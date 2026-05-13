# MVP Examples — Canonical Cases

The pattern: ridiculously narrow, ridiculously crappy, ship it. Every canonical example below was embarrassingly thin at launch. Each tested *one specific hypothesis* with the minimum technology and the maximum manual labor. Skills surface these anchors when the founder is feature-creeping or stalling on perfection.

## Airbnb v1 — Air mattresses at design conferences

What it was: a static page (AirBedAndBreakfast.com) listing the founders' own apartment with air mattresses, targeted at attendees of an industrial design conference in San Francisco when hotels were sold out. No payments — payment happened via PayPal or cash. No maps. No reviews. No mobile. No marketplace mechanics. Just three air mattresses and a phone number.

What it tested: would anyone book a stranger's apartment for short-term lodging? Yes. The conference forcing-function bypassed cold-start.

What the founders learned: trust is the unsolved problem (drove the host verification + reviews systems later). Photography matters disproportionately (drove Brian Chesky personally flying to New York to photograph hosts' listings).

## Twitch (Justin.tv) v1 — One streamer, one page

What it was: a 24/7 live stream of Justin Kan wearing a camera on his head. One streamer. One web page. Expensive custom backend (no LiveStream / YouTube Live yet). No gaming-specific support. No chat moderation. No multi-streamer features. No clip / VOD / mobile.

What it tested: would people watch live video from a stranger's perspective? Yes — but not at the level needed for a business. The pivot signal came from noticing which categories sustained engagement (gaming) vs which died (everything else).

What the founders learned: the original product hypothesis was wrong; the platform was right. Justin.tv became Twitch by cutting everything except gaming and rebuilding around it.

## Stripe v1 — Manual nightly bank faxes

What it was: a payments API that was end-to-end functional for one customer (YC startups). Backend bank integration was Patrick and John Collison manually faxing forms to bank operations each night to push transactions through. Almost no features. No fraud detection. No reporting dashboard. No tax handling.

What it tested: would developers actually integrate a payments API if the developer experience was good enough? Yes — and the manual operations layer was invisible to them, because Stripe absorbed the labor.

What the founders learned: the API was the moat; the operations were temporary cost. They charged from the first transaction.

## DoorDash v1 — Static page + founders deliver food

What it was: PaloAltoDelivery.com, a static webpage listing menus from local restaurants and a phone number. When someone called, the founders drove to the restaurant, picked up the food, and delivered it themselves. No driver network. No dispatching software. No marketplace logic. No restaurant integration. No customer accounts.

What it tested: would people in Palo Alto pay for food delivery from restaurants that didn't offer it? Yes. The founders also learned (by doing it themselves) every operational detail of the workflow that they'd later automate.

What the founders learned: delivery economics; restaurant pain points; the importance of speed signaling at the order page. None of this is in a Lean Startup chapter; it comes from being a driver for three months.

## Dropbox — The video MVP

What it was: a 3-minute video. Drew Houston recorded a screen-cast of how Dropbox *would* work — drag a file into a magic folder, see it appear on another machine. The product didn't exist; the video was the product test. Posted to Hacker News.

What it tested: would the target audience (developers who use multiple machines) opt into a beta if they saw the workflow? Beta signups jumped from 5,000 to 75,000 overnight.

What the founders learned: demand existed; the product was worth building. The video also became the most-watched MVP demo in startup history and is the canonical reference for testing demand for unbuilt software.

## Buffer — Two-step landing page

What it was: a two-page landing test. Page 1 described what Buffer would do (schedule tweets across times of day). The CTA was "Plans and pricing →." Page 2 showed three pricing tiers; clicking any tier surfaced "We're not quite ready yet — leave your email and we'll let you know."

What it tested: not "do people want this?" but "do people want this *enough to pay $X for it*?" The pricing-tier click was the signal — much higher quality than an email on page 1.

What the founders learned: the willingness-to-pay was real, and it segmented usefully across tiers. Joel Gascoigne started building Buffer with the funded validation in hand. The two-step is now a canonical Fake Door variant for any pricing-sensitive product.

## What these have in common

- **One acute customer.** Conference attendees. Justin Kan's audience. YC startups. Palo Alto food orderers. Drew's HN audience. Twitter power-users.
- **Manual everything that could be manual.** Faxes. Driving. Photographing. Recording.
- **Embarrassingly thin product.** No payments. No mobile. No accounts. No automation.
- **One falsifiable hypothesis.** "Will strangers book strangers' apartments?" "Will developers integrate a payments API?" "Will people pay for what we'll deliver by hand?"
- **Charged from day one** (in most cases). Money was the signal.

## What the founder should take from this

Whatever the founder is planning to ship probably has too many features. The MVP is not a small version of v1; it's the smallest possible experiment that tests the riskiest assumption. Michael Seibel: *"Be desperate to leave features out."*

The brick test: would your hair-on-fire early adopter use a brick if the brick solved the problem? If yes, ship the brick. If no, you don't have a hair-on-fire customer — you have a feature-list.

## Where this is used

`mvp-architect` cites these MVPs by name when scoping features. The founder almost always wants to add capability "because the user will need it eventually" — these examples are the refutation. If Airbnb didn't need maps, your v1 doesn't need search filters.
