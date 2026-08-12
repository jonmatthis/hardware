# RFQ Drafts: Student Mocap Kit

**⚠️ NOTHING HERE HAS BEEN SENT. No vendor has been contacted in any form.** These are drafts for
Paul to review, edit, and send from his own account when the team decides to open outreach.

> **Scope note (2026-08-11).** Current focus is the simple sellable bundle: Charuco board, webcams,
> tripods, cables. §6 and §7 are the drafts for that. Everything in §1 to §5 is deeper technical
> sourcing, parked for later rather than abandoned.

**Do the bench test first.** None of these emails are worth sending until you've tried three
candidate cameras at once on your own desk. The test tells you what to ask; the emails without it
just generate quotes for cameras you can't use.

When the time comes, the likely order is **ELP (§3) and the Alibaba factories (§4)** for a kit at
this price point, with **Arducam (§2)** as a lower-priority conversation, since their boards cost
about half a kit each. Send §1's acceptance criteria as an attachment with all of them. Don't blast
everyone the same day, because the answers from the first change the questions for the next.

---

## §1. The screening spec (attach to every RFQ)

Write this before anything else. It converts "find a cheap camera" into a pass/fail test, and it
doubles as the incoming-inspection procedure for every batch.

> **FreeMoCap Student Mocap Kit: camera acceptance criteria**
>
> **Must pass all:**
> 1. UVC 1.1+ compliant. Enumerates as a standard video device on Windows 11, macOS 15+, and
>    Ubuntu 24.04 LTS with **no vendor driver**.
> 2. **Three units stream simultaneously from one host at 1280×720 MJPEG ≥30 fps for 10 minutes
>    with no dropped device and no `No space left on device` error.** Tested on all three OSes.
> 3. Declared UVC isochronous bandwidth ≤ 90 Mbps per stream at the operating mode above.
> 4. MJPEG or H.264 output. YUY2-only is rejected.
> 5. Manual exposure control exposed via UVC (auto-exposure must be disableable). Auto-exposure
>    hunting across three cameras destroys multi-view consistency.
> 6. Fixed focus, or focus lockable. Autofocus that changes intrinsics mid-capture is a reject.
> 7. USB cable ≥1 m, detachable preferred.
> 8. Firmware and sensor part number **frozen** for the duration of the purchase order. Any change
>    requires written notice and a new sample.
>
> **Preferred:**
> - Global shutter
> - External hardware trigger input
> - M12 interchangeable lens
> - Stated FOV ≥90° diagonal

Test #2 will eliminate most candidates. Run it on Amazon-bought samples before spending a single
email on a vendor.

---

## §2. Arducam. DRAFT, NOT SENT

Lower priority for the $100 kit, since one B0332 is roughly half the kit budget. Keep this on file
for two reasons: Arducam answers technical email properly, and if a global-shutter or
hardware-triggered kit ever becomes a separate product, this is where that conversation starts.

> **Subject:** Volume quote + technical question, B0332 global shutter, multi-camera kit
>
> Hello,
>
> I'm with FreeMoCap, an open-source markerless motion capture project. We're putting together a
> three-camera kit for students and research labs and evaluating the B0332 (OV9281 global shutter
> USB) as the camera.
>
> Three questions:
>
> 1. **Volume pricing.** Could you quote the B0332 at 25, 50, and 100 units? We expect our first
>    production order to be in the 50 to 100 range, with repeat orders if the kit sells.
>
> 2. **Three-camera bandwidth.** Our application streams three B0332s simultaneously from one host
>    at 1280×800 MJPEG. Cheap UVC cameras often over-declare isochronous bandwidth and fail to
>    enumerate past two devices. What isochronous bandwidth does the B0332 firmware declare at
>    1280×800 MJPEG, and have you validated three units on a single USB 2.0 controller?
>
> 3. **External trigger.** Your documentation describes a reserved external trigger port. We want to
>    hardware-sync all three cameras from a single trigger source. Is there a recommended reference
>    design or connector part number for this, and does triggered mode change the effective frame
>    rate ceiling?
>
> A narrower question on the lens: the B0332 is listed with a 70° horizontal FOV and a
> non-interchangeable lens. For full-body capture in a small room we'd want closer to 90° to 110°
> horizontal. Do you offer a wide-FOV lens variant of this board, and what would the MOQ be?
>
> Thanks,
> [name / title / freemocap.org]

This template asks the two questions only they can answer (declared bandwidth,
trigger reference design), signals real volume without overstating it, and surfaces the FOV problem
early instead of after you've bought 100 boards.

---

## §3. ELP / Ailipu Technology. DRAFT, NOT SENT

> **Subject:** Quote request, 1080p UVC modules, 3-camera kit, 50 to 100 units
>
> Hello,
>
> We're an open-source motion capture project building a three-camera USB kit. We're looking at
> the ELP-USBFHD01M-L21 and similar modules.
>
> Could you quote at 25 / 50 / 100 units, and confirm the following:
>
> - Current sensor part number shipping on this SKU (we've seen OV2710 listed; please confirm)
> - Whether the firmware declares isochronous bandwidth low enough that **three** of these modules
>   stream simultaneously at 1280×720 MJPEG 30 fps from a single USB 2.0 host controller. This is
>   our hard requirement.
> - Whether manual exposure control is exposed over UVC and auto-exposure can be disabled
> - Available M12 lens options and FOV for each
> - Whether you offer a monochrome or global-shutter module in a similar price band
> - Lead time at 100 units, and whether firmware/sensor can be frozen for the order
>
> We'd like to purchase 3 samples first to validate the three-camera requirement before quoting a
> production order.
>
> Thanks,
> [name / title / freemocap.org]

---

## §4. Alibaba generic webcam factories. DRAFT, NOT SENT

Send the to 6 to 8 suppliers. Watch for whoever answers the bandwidth question with a real answer.

> **Subject:** 1080p USB webcam, 100 pcs, technical requirements attached
>
> Hello,
>
> We are a US open-source software project. We need 1080p USB webcams for a three-camera kit.
> Target quantity 100 pcs for the first order, with repeat orders if the product sells.
>
> Please quote at 100 / 300 / 500 pcs, FOB Shenzhen, and answer these questions:
>
> 1. What is the **exact sensor part number**? (Not "2MP CMOS", the part number.)
> 2. What isochronous bandwidth does the UVC firmware declare at 1280×720 MJPEG?
> 3. **Have you tested three of these cameras streaming at the same time from one computer?**
>    This is our most important requirement. If you have not tested it, please say so.
> 4. Is auto-exposure disableable through standard UVC controls?
> 5. Is the lens fixed focus?
> 6. Can you guarantee the same sensor and same firmware for the entire order, and for repeat
>    orders? We need every unit to behave identically.
> 7. What is the MOQ for a custom color box with our logo, and the additional cost per unit?
>
> We would like to buy 3 samples first. Please quote sample cost and shipping to the USA.
>
> Thank you,
> [name / freemocap.org]

**Note on question 3:** most will answer "yes, no problem." That answer is worthless. The point of
asking is to find the one supplier who says "we tested two, the third failed, here's what we did."
That supplier actually understands the product.

**Note on question 6:** this is the question that protects you. Generic factories substitute sensors
between runs as a matter of routine. Get it in writing, and keep a golden sample from the first
batch to check against.

---

## §5. Things NOT to ask yet

- Custom PCB, custom housing, custom firmware. That's OEM, MOQ ~500, and premature at 100 units or
  fewer.
- Tooling or NRE quotes. Nothing in this kit needs tooling.
- Exclusivity or distribution agreements.
- Anything about eye tracking. Keep the mocap kit conversation clean. The eye tracker is a
  different vendor set and a different sourcing game.

---

# For the simple bundle (current focus)

Shorter versions for the Charuco + webcams + tripods + cables bundle already announced on the shop.

## §6. Webcam suppliers, simple version. DRAFT, NOT SENT

> **Subject:** 1080p USB webcam quote, 100 pcs
>
> Hello,
>
> We're a US open-source software nonprofit. We sell a small motion capture kit and need 1080p USB
> webcams for it. First order around 100 pcs, repeat orders if it sells.
>
> Please quote at 100 / 300 / 500 pcs, FOB Shenzhen, and let us know:
>
> - Sensor part number
> - **Price with the microphone removed.** We do not want a microphone in this product.
> - Whether the lens is fixed focus (we need fixed, not autofocus)
> - Whether there is a 1/4-20 tripod thread, and whether a tripod is included
> - Whether the same sensor and firmware ships for the whole order and for repeat orders
> - Lead time at 100 pcs
> - MOQ and added cost for a custom color box with our logo
>
> We'd like 3 samples first. Please quote sample cost and shipping to the USA.
>
> Thanks,
> [name / freemocap.org]

Consistency is the question that matters here. A webcam that already ships with a tripod and clip
covers two bundle items in one line.

## §7. Charuco board printers. DRAFT, NOT SENT

The shop already sells this at $25 via Printify and says the service is slow and expensive.

> **Subject:** Quote, printed rigid board, 100 to 500 units
>
> Hello,
>
> We need a flat rigid printed board, 18"x24", single-sided, black and white pattern on 4mm
> corrugated plastic or similar. Print accuracy matters more than color quality, and the board
> needs to stay flat.
>
> Could you quote at 100 / 250 / 500 units, and let us know material options, flatness tolerance,
> and whether you drop-ship to end customers?
>
> Thanks,
> [name / freemocap.org]

Worth quoting local US sign shops alongside print-on-demand services. A yard-sign printer does this
exact job every day.
