# Rodent Eye Tracking: Scoping Note

*Research only, 2026-08-11. No one contacted. Dollar figures are order-of-magnitude.*

## Why this stream waits

The mocap kit is procurement and could ship this quarter. This is a five-figure engineering
engagement over 6 to 12 months. Running both at once means doing both badly.

The kit also builds what this stream will eventually need anyway: a working shop, a fulfilment
process, and evidence that people will buy FreeMoCap hardware.

That said, **the eval step is cheap and independent.** Buying one camera channel and proving
SkellyCam can pull frames off it doesn't compete with the kit for attention, and it de-risks the
whole stream for roughly $1.5k. If any budget goes here in the near term, it goes there.

## The hiring model

You're not buying parts, you're hiring a design house to build to your spec. You're the product
owner; the engineers are contractors.

Rough shape of the engagement:

- **Phase 0, feasibility.** Eval kits, prove three synced streams. Small fixed fee, and an explicit
  kill point.
- **Phase 1, breadboard.** First custom board plus a rough mount.
- **Phase 2, prototype.** Real flex, sub-4g mount, on an animal. Two or three iterations.
- **Phase 3, validated build.** Documented parts list and build guide.

Each phase is a separate payment. Two things to get right in the contract: **FreeMoCap owns all
design IP** (it fits the open-source mission), and **the split of work**.

**On the split:** doing CAD and software in-house and paying engineers only for the sensor-to-USB
electronics is the recommended structure. Mount geometry needs iteration against a live animal, so
keeping it in-house means iterating fast instead of paying per revision. Ballpark, that split cuts
the engineering bill meaningfully, though the numbers in the original design notes are estimates and
shouldn't be planned against until a real quote exists.

## What to correct from the original note

- "Framer (or soemthing?)" is **FRAMOS**.
- OmniVision direct is the wrong door at this size. Go through a distributor.
- Precision Optics is plausible but premium. Not the first call.
- The list was missing the open-hardware labs, which are probably the highest-value contacts:
  UCLA Miniscope, Sainsbury Wellcome, Open Ephys.

## Cable management

Tethered means all data and power go down the wire, with no on-head battery, which is what keeps
weight under 4g. Tangle gets solved with a commutator or slip-ring on a counterbalanced arm, which
is standard ephys kit and pairs well with NanEye's 3m no-distal-components spec.

## Open questions

- Who are the existing mouse-build collaborators, and what are they using today?
- Is torsion tracking required? If yes, rolling shutter is disqualifying and the sensor choice
  reopens.
- How many rigs in year one? Under ~20 and this is a collaboration to fund rather than a product.
- What's the current NanEye eval path, now that the NanoUSB2.2 boards read "not for new designs"?
