# UA5 — Stage 2 Analysis

The Stage 2 deliverable. Pulls together what exists in the space, who has a stake in the system beyond the users, who actually uses it, and what users are doing today when they need what the system would provide.

The sections are written in the order a reader would want to encounter them, but the student does not work on them in that order. Activities inform each other.

The positioning statement is revisited throughout. If any analysis contradicts a clause, the student revises `ua2-positioning-statement.md` — Stage 2 is the second pressure test on the statement.

---

## Landscape

A short survey of the space the system enters. Two or three pages of notes is usually enough.

### Adjacent products

- **eBird** (Cornell Lab) — Global giant for crowdsourcing bird checklists and modeling macro-level migration trends. Does well: massive dataset (36M+ checklists), trusted by researchers worldwide, Status & Trends maps for 495+ species. Gap: operates purely as a "what and where" log; cannot overlay bird sightings with local environmental maps. Built for serious birders and researchers, not non-expert conservation advocates.

- **NatureCounts** (Birds Canada) — Massive standardized open-data portal integrating specialized research data (breeding bird atlases, formal point counts) for professional conservation and policy tracking. Does well: rigorous, standardized data across regions. Gap: targets academic and professional data scientists; requires an official R package or massive raw database requests to merge and visualize sightings alongside local environmental layers. High barrier to entry.

- **BirdCast** (Cornell Lab) — Uses U.S. weather surveillance radar + machine learning for real-time nocturnal migration maps, predictive traffic forecasts, and "Lights Out" conservation alerts. Does well: cutting-edge real-time migration data. Gap: radar only detects total biomass moving through air — cannot identify which specific species are flying. Not useful for species-level population trend analysis.

- **Bird Conservation Network Tableau Tool** — Interactive dashboards for land managers to track site-level bird counts and 20-year regional breeding trends. Does well: clean, accessible dashboards for those who have access. Gap: rigid, static display for localized pre-packaged historical data (Chicago wilderness region only); not a dynamic tool for everyday users anywhere to map and cross-reference live field data with changing environmental layers.

### Open-source candidates

- **MapLibre GL** — Fast open-source map rendering library. License: BSD (permissive, no copyleft conflict). Use: direct frontend library install for overlaying bird data with environmental layers without building a mapping engine from scratch.

- **OpenBioMaps** — Customizable open biodiversity database platform. License: interoperate via API and backend JSON data transfers to avoid copyleft conflicts. Use: access to institutional biodiversity data and customizable database design for bird observations.

- **greenR** — R package for calculating local habitat health and urban canopy metrics. License: interoperate via API/JSON backend to avoid copyleft conflicts. Use: provides urban canopy math and habitat health scores that can be layered over bird population data without requiring users to run R themselves.

### Category

- The category customers think they're shopping in: "bird wildlife info" — simple, informational, low technical bar. Users search terms like "local wildlife status updates" or "city environmental reports," not "spatial ecology dashboard."
- What that category brings with it: expects simple browsing, quick answers, no setup, no data literacy required. Free or low-cost. Mobile-friendly. Not expecting to configure data layers or run trend analysis.
- Whether this is a fit or a misfit: Partial misfit. Birdpoint is more capable than what users think they're shopping for — multi-year NEON data, environmental overlays, trend analysis. The risk is that the entry point feels too complex and users bounce. The opportunity is to deliver depth that surprises them once they're in. The entry point must feel as simple as the category expects.

### Inherited conventions

Conventions the project is taking on whether it knows it or not. For each, decide explicitly: keep, break on purpose, or note as open.

- **Interactive map with bird photos** — Users expect to see birds on a map with visual identification. Keep.
- **Sighting log** — Users expect to be able to log their own bird sightings. Open — Birdpoint's primary use case is viewing population trend data, not personal logging; whether to include this feature is still undecided.
- **Species/location filtering** — Users expect to filter by species or location to find relevant information. Open — filtering is likely necessary but the specific implementation (search bar, map-based selection, dropdowns) hasn't been decided yet.

---

## Stakeholders and users

### Stakeholders

Everyone with a stake in whether the system succeeds beyond the users. Most stakeholders are not users. Most requirements come from stakeholders, not users.

| Stakeholder | Stake | Their version of "success" |
|---|---|---|
| NEON (National Ecological Observatory Network) | Data provider; federal funding justified by public use of their data | Data used accessibly by citizen scientists and land managers; no unauthorized automated scrapers or bots that drain portal infrastructure |
| Local conservation and wildlife restoration groups / rangers | On-the-ground impact; accurate information supports their work | App helps protect animals and wildlife in their area; data is accurate and doesn't mislead conservation decisions |
| Potential bad actors (poachers) | Could misuse precise location data for rare or sensitive species | N/A — this is a risk to manage, not a stakeholder to serve; Birdpoint should consider blurring or withholding exact coordinates for sensitive species |

### Users (recap from Stage 1, with Stage 2 updates)

- **Primary user type:** Engaged citizen who cares about conservation, wants bird population trend data in one accessible place to take action and spread awareness. Not a researcher or expert. Confirmed by interviews (sister — noticed birds disappear after construction and went looking for data; friend — birdwatcher who bridges multiple tools to understand ecological change).
- **Secondary user types:** Rangers and conservation professionals who may use Birdpoint as a quick public-facing reference or to share data with non-expert audiences.
- **What's been added or revised since Stage 1:** Secondary user type (rangers) identified in Stage 2. No changes to primary user type.

### Compliance and accessibility considerations

- **COPPA** — Expected users include people under 18. If users under 13 can create accounts or have personal data collected, parental consent is required. Needs a decision on minimum age or age-gating.
- **FERPA** — If Birdpoint is ever used in a school or classroom context, student data protections apply. Flag for later if educational use is pursued.
- **PII** — Optional account creation (for sharing sightings) would collect personal data at minimum (email, username). Standard data handling practices apply — don't collect more than needed, be clear about what's stored.
- **Location data sensitivity** — Precise coordinates for sensitive or rare species should be blurred or withheld to prevent misuse by poachers or bad actors. Precedent: eBird and iNaturalist both obscure exact locations for vulnerable species.

---

## Jobs-to-be-done and scenarios

One subsection per job. Each has the four-question structure plus at least one scenario.

### Job 1 — Understanding why local birds disappeared

- **JTBD statement:** When I'm curious about birds that have vanished near me, I want to learn what happened to them, so I can help them thrive in the future.
- **How do we know it's a real job:** Sister interview — she noticed birds disappear after nearby construction and spent an hour online searching for local wildlife status updates and city environmental reports. The need was real and unprompted.
- **What people do today:** Google the species name + location. May find species background and ID info. Hit a wall when looking for historical population data for that specific location — no consolidated source exists for non-experts.
- **Why has the current way persisted:** No better tool is known to the user. Google is the default because it's familiar and fast, even though it fails at the specific need (historical, location-specific trend data).

#### Scenario 1.1 — Birds gone after construction

She notices the birds that used to visit near her house have vanished since construction started nearby. She opens Birdpoint and searches for the species by name, but she types a similar-sounding bird and gets results for the wrong species — the population data doesn't match what she remembers seeing. She realizes the description doesn't fit and tries a different search with more detail. This time she finds the right species. She looks at the historical population trend for her area and sees a clear drop in the years overlapping with local development. She now has the context she was looking for and shares the trend chart with a friend.

**Reads back against positioning statement:** Yes — she accessed bird population data in one place (without hunting through multiple tools) to understand a local ecological change. Delivers the key benefit.

### Job 2 — Tracking bird recovery after an environmental event

- **JTBD statement:** When I'm tracking how birds are recovering after an environmental event like a wildfire, I want to see bird counts on a map of the burn scar, so I can see where populations are bouncing back.
- **How do we know it's a real job:** Origin interview — friend described going into spatial distribution data over a multi-year timeline after local wildfires to see if species were abandoning burn scars or returning as chaparral recovered. She treated it as a mini-research project.
- **What people do today:** Download official fire boundary maps from government portals. Request massive raw checklists from eBird. Manually write R and GIS scripts over an entire weekend to clean, merge, and plot overlapping data. Only then can a single trend line be plotted.
- **Why has the current way persisted:** No accessible alternative exists. The technical workflow is painful but it's the only path to the answer for someone with the skills to do it. Someone without those skills simply can't do it at all.

#### Scenario 2.1 — Post-wildfire species recovery

A wildfire happened a couple of years ago and she wants to understand how it affected bird populations in the area. She opens Birdpoint, navigates to the location, and filters for a specific species to see their population trend over the recovery period. Some of the most recent data hasn't been updated yet — the trend line cuts off earlier than she expected. She shifts the timeline back a few months to the last confirmed data and can see the recovery curve beginning to emerge. She gets the information she needed, even if the very latest data wasn't available.

**Reads back against positioning statement:** Yes — she accessed multi-year bird population trend data in one place without writing a single line of code, enabling her to understand the ecological impact of the wildfire. Delivers the key benefit.

---

## Open from this stage

Things flagged during Stage 2 that don't yet have a home — for the student to revisit later or carry into Stage 3.

- Sighting log feature — whether users can log their own sightings is undecided. Keep or drop? Affects screen inventory in Stage 3.
- Species/location filtering implementation — map-based selection vs. search bar vs. dropdowns? Open for Stage 3.
- Minimum age / age-gating — COPPA applies if users under 13 can create accounts. Decision needed before launch.
- Sensitive species location blurring — need a policy on whether to obscure exact coordinates for rare or vulnerable species.
- Data freshness — Scenario 2.1 surfaced that NEON data may lag. How stale is too stale, and how is this communicated to users?
