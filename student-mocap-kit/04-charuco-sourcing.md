# Charuco Board Sourcing

*Researched 2026-08-11. Nobody contacted. Goal: replace Printify print-on-demand with a bulk run
delivered to Boston.*

Current: $25 retail via Printify, print-on-demand, described on the shop as slow and expensive.

Spec: 18"x24", **double-sided, full color**, 4mm corrugated plastic. This is a standard yard sign,
which is the cheapest printed object in America.

---

## Two spec problems to settle first

**1. Show-through on double-sided 4mm coroplast.** A verified Printastic review says: *"when the
sun hits at certain angles, the other side shows through a little,"* and notes the same happened
with their previous supplier. On a decorative sign that's cosmetic. On a **calibration target it's
a faint mirrored Charuco pattern bleeding into the image**, which is exactly the kind of thing that
could confuse corner detection.

Options: ask for an opaque white block layer between sides, go 6mm or 10mm instead of 4mm (Boston
vendors offer up to 10mm), or make the board single-sided and cheaper.

**Worth asking: does the board actually need to be double-sided?** If it's two different patterns
that's one thing. If it's the same pattern on both sides for convenience, single-sided halves the
risk and cuts the cost.

**2. Print accuracy matters more than print quality.** A Charuco board that's scaled 2% off gives
silently wrong calibration. Any vendor quote needs a dimensional tolerance, and the first article
needs measuring with a ruler before the run is approved.

---

## Price reality

Printastic public ladder, 18"x24" 4mm coroplast (need to confirm whether these are 1- or 2-sided):

| Qty | Each |
|---|---|
| 10 | $8.99 |
| 20 | $6.99 |
| 50 | $6.49 |
| 100 | $4.99 |
| 250 | $4.69 |

So retail bulk is roughly **$5** against the current **$25**. Trade pricing should beat that again.

## Options, cheapest route first

| Route | Notes |
|---|---|
| **4over** ([4over.com](https://4over.com/4coro-coroplast-signs)) | Trade-only wholesale printer. Needs a reseller account. Cheapest per unit if we qualify. Warns that flutes create "a very subtle linear effect (faint lines)" on the surface, worth checking against corner detection. |
| **Printastic** | 800-575-5805 · hello@printastic.com · printed in USA, 6-color HP Latex. Public bulk pricing, no account needed. Good baseline quote. |
| **Boston local pickup** | [SpeedPro Boston North](https://www.speedpro.com/boston-north/yard-signs/) (pickup in Peabody or Lynnfield), [AlphaGraphics Boston Seaport](https://www.alphagraphics.com/us-massachusetts-boston-us598/signs/signs-by-type-material/coroplast), [Boston Banner Printing](https://bostonbannerprinting.com/services/), [Banners Etc.](https://www.banners-etc.com/corrugated-plastic-yard-signs) (MA). Yard Signs Boston offers 2mm to 10mm but **no pickup from their location**. |
| **eSigns, PrintDirtCheap, Gold Image, Blue Wave** | Other national bulk options worth a quote. |

Local pickup matters more than it looks: coroplast is bulky and light, so shipping 100+ boards is
expensive relative to the product. Driving to Peabody may beat freight.

---

## Suggested approach

1. Decide single vs double sided.
2. Get 5 quotes at 100 / 250 / 500: 4over if we can open an account, Printastic, and two or three
   Boston shops.
3. Order **one sample from the two cheapest**, measure it, photograph it under the lighting a
   student would use, and run it through calibration before committing.
4. Ask every vendor about show-through and dimensional tolerance explicitly.

## Fulfilment

Boards ship to the founder's apartment initially, storage later if volume justifies it. This is the
argument for buying in one batch rather than drop-shipping: at $5 a board, 250 boards is ~$1,250
and fits in a closet. That's a small enough bet to just make, and it removes Printify from the
critical path entirely.

Note the Shopify reliability complaint is mostly a **drop-ship** problem. Holding real stock in
Boston and shipping it yourself removes the supplier from the customer's experience.
