# Plumb

**Snap a photo of what's wrong. A vetted local pro prices it. Book and pay in the app.**

## The problem

Hiring someone to fix your home is slow and murky. You call around, wait for in-home visits, and get quotes for different equipment and different scopes, so you can't compare them. Most homeowners end up guessing whether a price is fair.

A lot of what they pay for isn't the work. It's the overhead of the company that sent the truck: sales visits, call centers, and layers of management. Good independent pros, meanwhile, spend hours driving out to quote jobs they don't win.

## What Plumb is

Plumb is a vertically integrated, full-stack home services company, delivered as an app. The photo does the site visit, the software does the admin, and the job goes straight to a vetted local pro.

The goal is to save homeowners about 30% on replacements starting out, and ultimately 50%, by stripping out overhead and unnecessary processes.

## How it works

1. **Snap it.** Take a photo of the problem, the error code, or the equipment label. Plumb reads the make, model and size, and tells you what's likely wrong.
2. **A pro prices the real job.** The photos and the read are the scope, so nobody drives out just to look. Repairs go to one vetted pro for that trade in your area, who sends back a price. Replacements, like an AC or a water heater, show an estimate right away.
3. **Book and pay in the app.** You approve the price, pick a time, and pay by card when the job is done. If the price needs to change once the pro sees the job, you approve that first.

## How the photo read works

- **Input:** one photo, the trade, and a few optional words.
- **Vision:** Claude reads the photo.
- **Facts come from a table, not from the model.** Plumb keeps its own knowledge base: 3,640 manufacturer error codes across 37 brands and 10 equipment types, plus 182 symptoms across 15 trades. Every entry was checked against the manufacturer's own text and carries its source.
- **Lookup is exact.** Codes are matched by brand and code, then the model picks the right row. What a code means and how serious it is come from the table. A code that isn't in the table comes back as "not in our list".
- **Output:** a plain summary, likely causes, what the pro will check, an urgent flag, and up to three follow-up questions.

It doesn't hand you repair steps, and a photo read never states a repair price. Accuracy isn't measured yet. The plan is a labelled photo test set and pros grading every read.

## What's built today
Plumb is a working iOS app with a live backend.

**For homeowners**
- Photo and label reading, with a manual fallback
- Error-code and symptom lookup
- AC replacement: pick a tier, compare vetted companies on the same system, book
- Water heater replacement with an instant estimate
- Repair requests, job status and history
- Quote Check: upload a quote you already have and see how it compares
- Saved card and one-tap payment, with your approval before any price change

**For pros**
- Sign in with a phone number, then a job feed for your trades and ZIP codes
- You set your own prices and upload your own price list
- One pro per trade per area, so you aren't bidding against five companies
- No lead fees
- Google Calendar sync and open-time scheduling
- Payouts to your bank through Stripe Connect

**For rental owners**
- Tenants send the photo, and the owner sees the read and approves the price

## Stack

React Native and Expo (iOS), Node.js and Express, PostgreSQL with Drizzle, Stripe and Stripe Connect for payments and payouts, Claude for reading photos, SMS and push for job updates.

## Status

- **Markets:** the Twin Cities (all trades) and Tampa Bay (HVAC). Starting narrow on purpose, so each local network works before the next one opens.
- **Goal:** the first 100 paying customers.
- **Where we are:** the first pros are joining in the Twin Cities, and the first rental portfolios are lined up to test it.

## Who's building it

I'm [Karu Thompson](https://x.com/KaruThompson), a 19-year-old founder in Minneapolis, building Plumb solo. I also run [Navo Lab](https://navolab.xyz), a growth agency for local service businesses, so I spend my weeks inside the same HVAC, plumbing and trades companies Plumb is built for. I've sat in their dispatch software and read their job costs, and that's where this comes from.

The app's source code is private. Want a walkthrough? Reach me on [X](https://x.com/KaruThompson) or [LinkedIn](https://www.linkedin.com/in/karuthompson/).
