# hardware

Hardware specs, plans, and strategies for FreeMoCap hardware offerings, headed for
[shop.freemocap.org](https://shop.freemocap.org).

Work is split into **two independent streams**. They share almost nothing: different vendors,
different budgets, different skills, different timelines. Keeping them separate is deliberate.

---

## [[student-mocap-kit/README|Stream 1: Student Mocap Kit]]

A 3-camera USB kit targeting $100.

| | |
|---|---|
| Sourcing game | Procurement. Zero custom electronics. |
| Vendors | Alibaba/Shenzhen webcam factories, ELP, Arducam |
| Skills needed | Purchasing, 3D printing, packaging, bench testing |
| Money at risk | Low four figures for a first batch |
| Timeline | Could ship this quarter |
| Status | Research. Nothing ordered, no vendor contacted. |

Next action: buy a few candidate cameras on Amazon and test three-at-once on all three OSes.

---

## [[rodent-eye-tracking/README|Stream 2: Rodent Eye Tracking]]

Head-mounted eye + world cameras for mice and rats. Sub-4g for mouse, tethered, multiple rigs at once.

| | |
|---|---|
| Sourcing game | Design-in. Real EE, a design partner, custom flex. |
| Vendors | FRAMOS first, then ams-OSRAM, plus the open-hardware labs |
| Skills needed | Contracted EE, in-house CAD and capture software |
| Money at risk | Five figures of engineering |
| Timeline | 6 to 12 months |
| Status | Parked pending the kit. The ~$1.5k eval step is cheap and can run independently. |

Next action: confirm the current NanEye eval path, then buy one channel and prove SkellyCam can
pull frames off it.

---

## Why the split

The original framing grouped these by price. They actually group by **how much custom electronics
each needs**, which decides who you even talk to. The mocap kit is a shopping problem. The rodent
tracker is a hiring problem. Treating them as one initiative means the hard one starves the easy one.

Shared background for both: `camera-hardware-design-notes.md` (buy-vs-design spectrum, jargon,
sensor shortlists, economics). Currently sits outside this repo, one directory up. Worth moving in
if we want it versioned alongside the streams.

---

## Conventions

- Every dollar figure in this repo is a **ballpark** unless explicitly marked `[verified]` with a
  date and a source.
- Any file containing outreach drafts says at the top whether anything has been sent.
- Vendor names appearing in research notes are **unvetted leads**, not recommendations.
