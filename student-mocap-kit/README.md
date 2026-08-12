# Stream 1: Student Mocap Kit

**Goal:** a simple 3-camera kit for student mocap, targeting $100.

**Sourcing game:** procurement. Zero custom electronics. This is a purchasing and packaging
exercise, not an engineering project.

**Status:** research. No vendor contacted. Nothing ordered.

---

## The original spec

*(Paul's notes, preserved as written)*

- Three cameras
	- Cheapo webcam style
	- USB/UVC complient
	- MJPG or H264 encoding
- Mounts (wall mount, desk clip, tripod)
- lights (optional)
- usb extension cables
- Charuco board
- Alternatibely - raspberry pi or similar that can run the whole thing

### Companies to talk to
- Arducam?
- Omni vision
- Ali Baba / Shenzen factories that sell cheapo usb cams
	- esp ones that look like this: ![[reference-generic-webcam.png]]

---

## Where the research landed

The kit's job is to delete the three things FreeMoCap's own
[hardware requirements page](https://docs.freemocap.org/documentation/software-hardware-prerequisites.html)
currently leaves to the user:

1. **Which cameras.** The docs recommend three and name zero specific models.
2. **A Charuco board.** "Users will need to print out a Charuco board," flat and correctly scaled, on their own.
3. **Physical setup.** Extension cables and tripods, listed as "convenient" but not provided.

Two things the docs settle for us:

- **No USB hub in the kit.** The docs say plug cameras straight into the computer, and hub support
  is explicitly still being worked on. Shipping a hub would contradict our own guidance.
- **Multi-camera USB is a known open problem.** Which is why any candidate camera gets tested
  three-at-once before we order quantity.

Cameras in the $8 to $14 range make $99 work. Global shutter would be nicer for fast motion and
starts around $50/camera, so it's out of scope for this kit and parked.

**Cheapest first move:** ship an accessory kit with no cameras (mounts, cables, Charuco, quickstart)
and publish a list of webcam models we've verified run three-at-once. Both cost bench time rather
than inventory.

## Docs in this stream

| File | What's in it |
|---|---|
| [[01-sourcing-notes]] | What the kit is for, camera options, ballpark costs, the Shenzhen question |
| [[02-rfq-drafts]] | Camera acceptance criteria + unsent RFQ drafts for ELP, Alibaba, Arducam |

## Next actions

1. Buy 3 each of a few candidate cameras on Amazon. Test three-at-once on Windows, macOS, Linux.
2. Publish the tested-camera list.
3. Design and print the mount and Charuco board. Ship the accessory kit.
4. Revisit the camera-included kit once we know which cameras work.

## Open questions

- Is the Raspberry Pi variant (a box that runs the whole pipeline) a real product or a distraction?
  It changes this from procurement into a software-support commitment.
- Do we want optional lights in the kit, or is that scope creep?
- Do we sell through shop.freemocap.org directly, or drop-ship?
