# Student Mocap Kit: Sourcing Notes

*Research only, 2026-08-11. No vendor contacted. **Every dollar figure here is a ballpark** meant
for deciding whether a direction is worth pursuing, not for planning against. Only two prices were
read off a live page and they're marked [verified].*

---

## 0. What the kit is actually for

From FreeMoCap's own hardware requirements page, the three things a new user has to solve alone:

1. **Which cameras.** The docs recommend three cameras and name zero specific models. Every student
   picks blind, and some of them pick wrong.
2. **A Charuco board.** "Users will need to print out a Charuco board." Printing it flat, rigid, and
   at the correct scale is on them.
3. **Physical setup.** Extension cables and tripods are called "helpful... but not necessary, just
   convenient," which is true right up until you try to place three cameras around a room.

The kit's job is to delete those three problems for $100. That's the whole pitch. It doesn't need
better cameras than what people already use, it needs *known-good* ones plus the boring parts.

**One thing the docs settle for us:** *"These cameras should be connected directly to the computer's
USB ports. We are working on support for using multiple cameras through a single USB hub, but for
now, we recommend plugging the cameras straight into the computer."* So **don't put a hub in the
kit.** It would contradict your own documentation. Ship the extension cables instead.

---

## 1. The one thing worth being careful about

Multi-camera USB is the failure mode your docs already warn about, and there's a specific
mechanism behind it worth knowing when picking a camera.

USB 2.0 reserves bandwidth based on the peak rate a camera's firmware *declares*, not what it uses.
Plenty of cheap webcams declare far more than they need, so two enumerate and the third fails. It's
a firmware property, it's invisible on any spec sheet, and it can differ between production runs of
the same model.

Practical consequence, and this is the only hard rule in this document:

> **Buy samples and test three-at-once before ordering any quantity.**

Everything else here is negotiable. That isn't. It's also cheap to do: a few hundred dollars of
Amazon orders and an afternoon with SkellyCam on Windows, macOS, and Linux.

Secondary preferences, in rough order of how much they matter:

- **MJPEG or H.264 output**, not YUY2-only. Uncompressed 1080p will never fit three streams.
- **Disableable auto-exposure.** Three cameras independently hunting exposure is bad for multi-view.
- **Fixed or lockable focus.** Autofocus changes intrinsics mid-recording and quietly corrupts calibration.
- **Global shutter** is genuinely better for fast motion, and it's also ~$50/camera minimum, which
  puts it out of a $100 kit. Worth knowing about, not worth designing the kit around. Park it.

---

## 2. Camera options, roughly

| Option | Rough cost each | What you get | What you risk |
|---|---|---|---|
| **Generic Shenzhen webcam** (the type in the pasted image) | ballpark $8 to $14 at 100 | Hits the price target with room to spare | No continuity. Factory swaps sensor and firmware between runs without telling you. |
| **ELP / Ailipu board modules** | ballpark $20 to $30 at 100 | Answers technical email in English, will tell you the actual sensor part number | Tighter on price. Probably a $130 to $150 kit, not $99. |
| **Arducam** | $49.99 [verified] for the global-shutter board, ~$56 [verified] for a color rolling one | Real documentation, real support, US-friendly | Roughly 1.5× the entire kit budget in cameras alone |

Named Alibaba suppliers that came up in listings, **unvetted and uncontacted**: Shenzhen Sunrupid,
Hongzexin, Goldever, Oddvans, Kolitt. A search starting point, nothing more.

The generic-webcam risk is manageable at your volumes: buy the whole run at once and keep one unit
from the batch as a reference to check future orders against.

---

## 3. Rough cost picture

Ballparks. Treat the shape as meaningful and the digits as noise.

**A $99 kit at ~100 units** lands somewhere around **$45 to $60** in parts and freight:

- 3 generic cameras: the dominant line, maybe $25 to $40 of it
- 3 active USB extension cables (5m, must be active): ~$10
- 3 stands with clamp mounts: ~$39 at retail, less in bulk. See `07-builds-and-prices.md`.
- A Charuco board on 3mm PVC: ~$5
- Box, insert, printed quickstart: ~$3

That's workable margin at 100 units, thin-to-pointless at 10 because sample-quantity camera pricing
eats it. Camera cost swamps everything else, so that's the only line worth negotiating.

Not in that number, and worth saying out loud: **assembly and fulfilment is real work.** Call it
20 to 30 minutes a kit, so 100 kits is a week of someone's time. And support burden across three
operating systems is ongoing.

At this volume the kit isn't going to fund anything. It's worth doing because it makes FreeMoCap
work out of the box for someone who buys one thing, and because it's how you find out whether a
hardware business is real before betting on one.

---

## 4. A cheaper first move

**Ship the accessory kit first: stands, cables, Charuco board, quickstart. No cameras.**

No firmware roulette and no USB support tickets from cameras you sold, since the customer brings
their own. Everything in it is off-the-shelf and buyable today.

Paired with it, the highest-value thing you can produce costs nothing but bench time: **a maintained
list of specific webcam models verified to run three-at-once on each OS.** Your docs currently name
no models. That list fills a documented gap, helps every user whether or not they buy anything, and
it's also the prerequisite for ever shipping a kit with cameras in it.

---

## 5. On flying to Shenzhen

Not yet, and the reason is just that there's nothing to negotiate. At 100 units you're buying stock
parts that samples and email will get you. A trip earns its cost when you want your own enclosure,
your own silkscreen, and a locked firmware revision, which is OEM territory and MOQ around 500.

Sell some kits, find out if demand is real, then go with something to ask for. A Shenzhen sourcing
agent (typically 3% to 5% of order value) covers most of the same ground in the meantime.

---

## 6. Next actions, all in-house

1. Buy 3 each of a few candidate cameras on Amazon. Test three-at-once on all three OSes.
2. Publish the tested-camera list. This is useful on its own and blocks nothing.
3. Design and print the mount and a Charuco board. Ship the accessory kit.
4. Revisit the camera-included kit once you know which cameras actually work.

---

## Sources

- [FreeMoCap hardware/software requirements](https://docs.freemocap.org/documentation/software-hardware-prerequisites.html)
- [freemocap.github.io repo README](https://github.com/freemocap/freemocap.github.io)
- [Arducam B0332 OV9281 global shutter USB camera](https://www.arducam.com/arducam-120fps-global-shutter-usb-camera-board-1mp-720p-ov9281-uvc-webcam-module-with-low-distortion-m12-lens-without-microphones-for-computer-laptop-android-device-and-raspberry-pi.html)
- [Arducam B0201 IMX291 USB camera module](https://www.arducam.com/arducam-1080p-low-light-wdr-usb-camera-module-for-computer-2mp-1-2-8-cmos-imx291-120-degree-wide-angle-mini-uvc-spy-webcam-board-with-microphone-3-3ft-1m-cable-for-windows-linux-mac-os.html)
- [ELP USBFHD01M-L21](https://www.elpcctv.com/elp-full-hd-usb-camera-module-1080p-usb20-ov2710-color-sensor-mjpeg-with-wide-angle-21mm-lens-p-204.html)
- [Multiple UVC cameras on Linux, bandwidth reservation](https://www.thegoodpenguin.co.uk/blog/multiple-uvc-cameras-on-linux/)
