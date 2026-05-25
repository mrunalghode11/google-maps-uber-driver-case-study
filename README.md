# Google Maps — Uber Driver Pickup Accuracy
## A PM Case Study
### By Mrunal Ghode | Aspiring Product Manager

---

## The One Line Problem Statement

Uber drivers and customers face wrong gate pickups due to 
GPS drift of up to 200 metres in dense Indian cities, 
causing trip delays, frustration, and lower ratings.

---

## 2. Root Cause Analysis

### Root Cause 1 — Outdated Map Data
In India new construction happens overnight. It is 
impossible for Google to update map data every 24 hours 
across millions of locations. Too slow and too expensive 
to fix quickly.

### Root Cause 2 — User Error / Imprecise Pinning
Customers drop inaccurate pins assuming the driver will 
figure it out. They don't realise their pin is 200 metres 
from the actual pickup gate.

### Why I chose Root Cause 2
Root Cause 1 is an infrastructure problem that takes 
years to fix. Root Cause 2 is a product design problem 
that can be solved in weeks. You cannot force millions 
of users to pin correctly — but you can design the app 
to make accuracy the default.

---

## 3. CIRCLES Framework Analysis

### C — Comprehend the Situation
**Goal:** Reduce failed or delayed pickups caused by 
inaccurate pins on Google Maps

**Platform:** Mobile — Android and iOS

**Business context:** Every failed pickup costs Uber a 
trip rating, a driver's time, and potentially a customer. 
At scale across millions of daily trips in India, this 
is a significant retention and revenue problem.

---

### I — Identify the User

**Primary user: The Uber Driver**

Meet Ramesh. He drives Uber full time in Mumbai.

- Age: 28–45
- Works 10–12 hours a day
- Depends on trip ratings for bonuses
- Gets penalised for cancellations
- Loses 15–20 minutes per wrong pickup
- Makes 4–5 wrong gate pickups every single day
- Has to call the customer almost every trip in 
  dense areas like Hiranandani Estate or BKC

**Secondary user: The Uber Customer**

- Drops a pin quickly without thinking about gate accuracy
- Assumes the driver will call and figure it out
- Gets frustrated when the driver is late or confused
- Leaves a low rating even though the pin was their fault

---

### R — Report the User's Needs

**Need 1 — Pin accuracy without extra effort**
Ramesh needs the pin to be accurate by default. 
He cannot afford to call every customer and waste 
time. He needs the app to do the heavy lifting for him.

**Need 2 — Gate-level pickup clarity**
In large complexes like apartment buildings, malls, 
and hospitals — Ramesh needs to know exactly which 
gate to go to before he even starts driving.

**Need 3 — Fewer customer calls**
Every call Ramesh makes to a confused customer adds 
stress and wastes time. He needs the pickup location 
to be self-explanatory without any back and forth.

---

### C — Cut Through Prioritisation

| Need | User Impact | Business Impact | Effort | Priority |
|---|---|---|---|---|
| Pin accuracy by default | High | High | Low | 🔴 P0 |
| Gate-level clarity | High | High | Medium | 🟡 P1 |
| Fewer customer calls | Medium | Medium | Low | 🟢 P2 |

**Prioritising Need 1 — Pin accuracy by default**

If the pin is accurate from the start, Needs 2 and 3 
solve themselves. Gate clarity and fewer calls are 
downstream consequences of an accurate pin. Fix the 
root first.

---

### L — List Solutions

**Option A — GPS Auto-Snap**
Automatically snap the customer's pickup pin to their 
exact current live location when booking. Remove the 
default manual pinning behaviour that causes drift.

**Option B — Landmark-Based Pickup Points**
Use historical trip data from thousands of past Uber 
pickups at the same location to suggest the most 
common pickup gates. Show the customer a dropdown — 
North Gate, South Gate, Main Entrance — ranked by 
how often drivers actually stopped there.

**Option C — Confirmation Popup**
Before the customer finalises their pin, show a 
confirmation popup: "Is this your exact pickup location?" 
with a clear map view. Forces a conscious check 
before booking.

---

### E — Evaluate Tradeoffs

**My pick: All three — shipped in phases**

**Phase 1 — Option A (GPS Auto-Snap)**
Fastest to build. Ships in 2 weeks. Immediately 
improves pin accuracy for majority of users in 
open areas. Low engineering effort, high impact.

**Risk:** GPS itself drifts by up to 200 metres in 
dense cities due to signal bounce between tall buildings.
**Mitigation:** Phase 2 solves exactly this.

**Phase 2 — Option B (Landmark-Based Pickup Points)**
Uses historical trip data to surface the most accurate 
gate options at complex locations. Addresses GPS drift 
in dense urban areas. Ships in 6 weeks.

**Risk:** Needs sufficient historical data per location 
to be useful. New locations with few past trips won't 
have enough data.
**Mitigation:** Default to Option A for locations 
with less than 100 historical trips.

**Phase 3 — Option C (Confirmation Popup)**
Final safety net. Even if Options A and B produce a 
slightly inaccurate pin, the popup gives the customer 
one last chance to correct it consciously. Ships in 
1 week — lowest engineering effort of all three.

---

### S — Summarise

Uber drivers in dense Indian cities lose 15–20 minutes 
per shift to wrong gate pickups caused by inaccurate 
customer pins.

I'd solve this in three phases:
1. Auto-snap pin to live GPS location by default
2. Landmark-based pickup point suggestions using 
   historical trip data
3. Confirmation popup as a final accuracy check

Start with Phase 3 — ships fastest. Then Phase 1. 
Then Phase 2 once data infrastructure is ready.

Measure success by reduction in driver-to-customer 
calls per trip and improvement in post-trip ratings.

---

## 4. Success Metrics — HEART Framework

| Framework | Metric | Target |
|---|---|---|
| Happiness | CSAT rating from drivers and customers after 
landmark-assisted trips | Above 4.3/5 |
| Engagement | % of users opening landmark dropdown weekly | Above 60% |
| Adoption | % of new users selecting a landmark on their 
first booking without guidance | Above 40% |
| Retention | Driver retention on Google Maps navigation 
for Uber trips | 10% lift in 60 days |
| Task Success | % of trips completed without driver 
calling the customer | Above 85% |

---

## 5. What I Learned

- Always find the root cause before jumping to solutions
- The best solutions make accuracy the default — 
  don't rely on users to do the right thing
- Phase your solutions by engineering effort and impact — 
  don't try to build everything at once
- Historical data is a product feature, not just 
  an analytics tool
- Challenging your own solution ("but Uber already 
  has current location") leads to deeper thinking 
  and better products

---

## 6. My Personal Angle

I built this case study entirely from first principles — 
starting with a simple observation that Uber drivers 
face wrong gate pickups, and working backwards to 
understand why, and forwards to design what to build.

My background in Business Analytics shaped how I 
approached this — using historical trip data not 
just to understand the problem but to power the 
solution itself. Data isn't just for reporting. 
It's a product feature.

---

*Case study by Mrunal Ghode — Aspiring Product Manager*

*Built using the CIRCLES framework and HEART metrics.*

*Every insight in this case study came from first 
principles thinking — no templates, no copying.*

*📧 Connect: www.linkedin.com/in/mrunal-ghode*
*🔗 Portfolio: github.com/mrunalghode11*
