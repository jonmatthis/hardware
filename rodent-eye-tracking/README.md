# Stream 2: Rodent Eye Tracking

**Goal:** head-mounted multi-camera eye tracking for mice and rats. Two eye cameras plus one world
camera, tethered, feeding synchronized video into a recording pipeline. Multiple rigs running at once.

**Sourcing game:** design-in. This is the only build that needs real electrical engineering and a
design partner. Nothing about the mocap kit's vendor process transfers here.

**Status:** parked pending the mocap kit. Research only, no one contacted.

---

## The original spec

*(Paul's notes, preserved as written)*

- Three cameras (two eye, one world) mounted on a mouse head
- must be sub-4g
- tethered through the roof, passive or active cable management
- feed into some kinda computer for recording and monitor
- Must be able to run multiple at the same time

---

## Mouse and rat are two different builds

Worth splitting explicitly, because the constraints diverge:

| | Mouse | Rat |
|---|---|---|
| Weight budget | sub-4g, the hard constraint | far more forgiving (~300 to 500g animal) |
| Tether | required, all power and data down the wire | tempting to go wireless |
| Sensor class | sub-mm, mono (NanEye class) | same parts work, more mechanical freedom |

**The rat wireless flag:** low-weight, low-latency HD video over wireless is a genuinely hard
problem, which is why UCLA Miniscope still tethers. Realistic options are to tether the rat too, or
accept compressed/lower-res wireless in a small backpack. Worth deciding early so "rat = wireless"
doesn't become the hardest problem attached to the smallest payoff.

## Three things that shape everything else

1. **Sub-4g with 3+ cameras is already published.** Meyer et al. use 180 mg analog micro-cameras;
   a four-camera headset is 1.64g, and 3.51g even with an ephys headstage and microdrive. The target
   sits below a solved result. Fork existing rigs, don't start blank.

2. **Two sensor paths.** Analog micro-cameras (the Meyer route) are cheapest, lightest, proven, with
   analog out to a cheap USB capture. NanEye / NanEyeM is a 1mm² digital sensor that drives signal
   down a 3m cable with zero components at the head end, which is close to purpose-built for a
   tethered rodent rig, but it's rolling shutter and a design-in part.

3. **Eval before engineering.** Roughly $1.5k buys one channel and proves SkellyCam can pull frames.
   Roughly $5k proves three synced. Both happen before hiring an EE, and both sit squarely in a
   Python skillset. The old NanoUSB2.2 base stations read "not for new designs," so the current eval
   path needs confirming.

## Companies to talk to

*(corrected and expanded from the original note)*

| Who | Why |
|---|---|
| **FRAMOS** | Distributor with ams-OSRAM and OmniVision access **plus design-in engineering support**. The first call. Paul's note said "Framer (or soemthing?)" and this is the company. |
| ams-OSRAM | Makes NanEye / NanEyeM. Go through FRAMOS rather than direct. |
| Precision Optics | Plausible for the micro-optics, but a premium medical-optics shop. Expect premium pricing. |
| OmniVision | Wrong door at our size. Distributor instead. |
| UCLA Miniscope (Aharoni) | Built this class of rig already. Open hardware. |
| Sainsbury Wellcome Centre | Open hardware, rodent-specific mechanics. |
| Open Ephys | Commutators, headstages, the tethering ecosystem. |

For mouse-specific mechanics, collaborating with the open-hardware labs is likely better than a
commercial design house, and it fits the open-source mission.

## Docs in this stream

| File | What's in it |
|---|---|
| [[01-scoping-note]] | Why this waits, the hiring model, open questions |
| [[02-contacts]] | Contact info for everyone in the table above |

## Open questions to resolve before spending anything

- Who are the existing mouse-build collaborators, and what are they running today?
- **Is torsion tracking required?** If yes, NanEyeM's rolling shutter is disqualifying as a final
  sensor and the sensor choice reopens. This is the single question that most changes the budget.
- How many rigs, realistically, in year one? Under ~20 and this is a collaboration to fund rather
  than a product to manufacture.
- Mouse first or rat first? Rat is mechanically easier and might de-risk the pipeline sooner.
