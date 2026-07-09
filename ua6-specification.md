# UA6 — Specification

The Stage 3 deliverable. Pulls everything from Stages 1 and 2 into a single document that a developer — human or AI — can build from.

The screens are the spine. In a small project the screens are the functional requirements: each screen names what the system does in terms a user would recognize.

MVP scoping is not a section in this document. Which screens get built first emerges during wireframing as the deadline forces choices, not from a planning artifact written before the work begins.

---

## Overview

### Positioning statement

> For an engaged citizen who cares about conservation and wants to learn more about birds and wants all the data and info in one app
> who wants to have data points of each species of bird in a location in one place to take action and advocate for the birds in the habitat and spread awareness,
> the Birdpoint is an interactive data tool
> that gives users accessible bird population data to identify at-risk species and take informed conservation action.
> Unlike Google, eBird, and other tools not designed for non-experts,
> our product allows users to see trends of the bird data points all in one place and accessible to non-experts.

### Summary

Birdpoint is a map dashboard for student researchers, curious citizens, and conservation professionals like rangers who want to see information about birds and their populations — including how they're responding to events like wildfires or habitat loss. It takes data from professional science networks (NEON) and combines it with local bird sighting numbers. Instead of spending a weekend cleaning spreadsheets or writing GIS and R code, you type in a place and see the data. ML/regression features are a future goal.

---

## Screen inventory

A flat list of every screen the system needs.

| # | Screen | Purpose (one sentence) | Scenarios that pass through it |
|---|--------|------------------------|--------------------------------|
| 1 | Home | Entry point where the user chooses what to do — explore the map, log a sighting | Both scenarios |
| 2 | Map | Interactive map showing bird data by location; tap a location to explore it | Both scenarios |
| 3 | Location Detail | Shows bird species present at a selected location with search; includes empty state if no data | Both scenarios |
| 4 | Species Detail | Shows population trend data for a specific species at a location, including AI conservation suggestions | Both scenarios |
| 5 | Log Sighting | Form for recording a bird sighting at a location; includes confirmation state and returns to map | Neither scenario (user-initiated action) |

---

## Screen descriptions

### Screen 5 — Log Sighting

- **Purpose:** Allows the user to record a bird sighting at a location and submit it.
- **Who lands here:** Any user who taps the Log Sighting button from Home.
- **What's shown:** Species selector, location selector, optional photo upload button, optional description text field, Submit button.
- **What they can do:**
  - Select a species
  - Select a location
  - Take or upload a photo (optional)
  - Write a description (optional)
  - Submit the sighting
- **Where each action goes:**
  - Submit → Confirmation message shown on this screen, then navigates to Map screen centered on the logged location

---

### Screen 4 — Species Detail

- **Purpose:** Shows population trend data and conservation information for a specific bird species at a selected location.
- **Who lands here:** Any user who taps a species from the Location Detail screen.
- **What's shown:** Species photo, introductory paragraph about the species, population trend graph (historical NEON data), data table (shown inline below graph when expanded), AI-generated conservation suggestions section.
- **What they can do:**
  - Tap graph to expand data table inline
  - Ask the AI a question about the species or conservation
- **Where each action goes:**
  - Tap graph → Data table expands inline below the graph on the same screen
  - Ask AI → AI responds inline within the conservation suggestions section; stays on this screen

---

### Screen 3 — Location Detail

- **Purpose:** Shows the bird species present at a selected location with a searchable list.
- **Who lands here:** Any user who taps a pin on the Map screen.
- **What's shown:** List of bird species found at this location, each with name and photo. Search bar to filter by species. Empty state ("no results") if the search finds nothing or the location has no data.
- **What they can do:**
  - Search for a species
  - Tap a species in the list
- **Where each action goes:**
  - Search for a species → List filters to matching species; shows "no results" if none found
  - Tap a species → Species Detail screen for that species at this location

---

### Screen 2 — Map

- **Purpose:** Shows locations with available bird data on an interactive map so the user can navigate to a location.
- **Who lands here:** Any user who taps the Map button from Home.
- **What's shown:** Interactive map with pins marking locations that have NEON bird data. Search bar for finding a specific location.
- **What they can do:**
  - Tap a pin
  - Search for a location
- **Where each action goes:**
  - Tap a pin → Location Detail screen for that location
  - Search for a location → Map pans to that location; if a matching pin exists, it is highlighted

---

### Screen 1 — Home

- **Purpose:** Entry point where the user chooses what to do — explore the map or log a sighting.
- **Who lands here:** Any user when they first open the app.
- **What's shown:** Birdpoint logo, short description of what the app does, Map button, Log Sighting button.
- **What they can do:**
  - Tap Map button
  - Tap Log Sighting button
- **Where each action goes:**
  - Map button → Map screen
  - Log Sighting button → Log Sighting screen

---

## Requirements

- Sensitive or rare species coordinates must be obscured or generalized to prevent misuse (e.g., poaching or nest disturbance).
- App must be usable without creating an account; no PII collected in v1.
- Every data view must show when the data was last updated so users know how current it is.
- User-logged sightings are publicly visible on the map to all users.

---

## Constraints and assumptions

- Primary data source is NEON (2017–2022); coverage is limited to NEON monitoring sites across the U.S. Locations outside NEON coverage will show no data.
- No user accounts in v1; no PII collected.
- AI conservation suggestions are generated via the ChatGPT API based on species and location context.
- ML/regression features are out of scope for v1.

---

## Open questions

- What happens when a user tries to log a sighting for a location with no existing NEON data — does the sighting still appear on the map?
- How are user-logged sightings displayed relative to NEON data — same pins, different color, separate layer?
- What is the threshold for obscuring a species' location — any species flagged as threatened/endangered, or a specific list?
