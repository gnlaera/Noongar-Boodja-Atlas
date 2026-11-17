# Noongar Boodja | Geographic & Language Atlas

**Version 4 · 17 November 2026**

A single-file interactive atlas (`index.html`) for exploring **indicative** Noongar language-group geography in south-western Western Australia. The Atlas is a geographic reference, not a legal or cultural determination of Traditional Ownership, native title, language authority, or Aboriginal heritage status.

## Contents

- **12 language-group polygons**, with 3,418 ring vertices and 3,401 connecting segments, retained from the user-supplied source shapefiles.
- **290 curated reference places**, including cities, towns, natural landmarks, heritage sites, industrial facilities and mines. Many are indicative pins rather than surveyed site centres.
- **98 language-name records**, with common, historical and source-map variants, including caution flags for ambiguous names.
- Coordinate lookup, nearest mapped edge distance, on-line group candidates, nearby group boundaries, map filters, share links and CSV exports.
- Address and postcode lookup via optional **Geoapify forward geocoding**, with user-selected candidates displayed as map markers. The site operator must supply an origin-restricted API key before the public geocoder is active.
- Browser-permitted device geolocation on mobile and desktop, with an indicative reported accuracy radius, visible map centring and language-group classification.
- Three basemaps: Geoscience Australia topographic, Esri terrain/roads and Esri satellite imagery. Optional WA government WMS overlays for conservation, mines, rivers, wetlands and mining tenements.

## New in version 4

- **Unified search:** The existing search box continues to find all embedded places, Noongar group names/aliases and decimal GPS coordinates without any external service. It also offers an explicit **Find address or postcode** action for online searches. The external query is sent only on user submission, not at every keystroke.
- **Real addresses and postcodes:** Configured Geoapify returns selectable matches for street addresses, suburbs and postcodes within the atlas's south-west WA geographic scope. Postcode results are identified as **area reference points**, not property coordinates. Results are run through the atlas's existing polygon and mapped-boundary calculations.
- **Device location:** Tap **GPS / Use my location** on phone or desktop. The browser asks permission, recentres the map and shows the reported accuracy radius as a circle. Desktop accuracy may be coarse if derived from network/Wi-Fi signals. The device's coordinates are not transmitted to the external geocoder.
- **Map framing:** Existing bottom-sheet-aware placement is retained. The GPS precision automatically selects a suitable zoom level.
- **Privacy and resilience:** Address queries are third-party requests, with the provider identified in About. Embedded places, language groups, map-click lookup and GPS continue to work when no geocoding key is configured or the provider is unavailable.

### Enable address and postcode searching for the public site

1. Create a [Geoapify account and free API key](https://www.geoapify.com/get-started-with-maps-api/). The published free allowance is currently 3,000 credits/day for a project, with one forward-geocode query charged one credit; verify current pricing.
2. In Geoapify's API key settings, restrict permitted referrers/origins to the real GitHub Pages website (typically `https://gnlaera.github.io` and the exact Atlas page URL as supported by the provider). Do not use a privileged unrestricted key in publicly readable HTML.
3. Open `index.html` and locate this line near the start of the application script:

   ```js
   const GEOAPIFY_KEY = ''; // OWNER SETUP
   ```

   Replace the empty quotes with your **origin-restricted browser key**. The key is visible to anyone viewing the HTML source; referrer/origin restrictions and quota controls are essential.
4. Commit the updated `index.html`, and verify live searches such as `6000`, `Bunbury WA`, or `200 St Georges Terrace, Perth WA` from your GitHub Pages URL. Confirm the returned candidates and whether they are property, street, town or postcode reference points.
5. Keep [Geoapify](https://apidocs.geoapify.com/docs/geocoding/) and OpenStreetMap attribution visible. Check and comply with the provider's privacy terms and usage limits. No external geocoding query is sent until the visitor selects the online search action.

**Without this key, only the new external address/postcode lookup is inactive; all existing atlas searches and device-location functions remain operational.** It is not possible to keep a browser-delivered key secret inside a static public GitHub Pages site.

## Previously added in version 3

- **Mobile map-first layout:** draggable, keyboard-accessible bottom explorer with collapsed, preview and expanded positions; optional Map Only mode.
- **Readable result preview:** selected place, mapped group, edge classification and nearest mapped edge without opening all metadata.
- **Improved boundary interpretation:** proximity only to the containing polygon’s edge is labelled **near outer edge**, not automatically **near another language group**. Multiple mapped-line candidates continue to be returned at group borders or junctions.
- **No overlapping mobile zoom/coordinates:** zoom controls are moved to the upper right, while coordinates appear temporarily after selections, away from the zoom stack and mobile sheet.
- **Simpler navigation:** a persistent mobile search entry point, compact legend, reduced permanent disclaimers, collapsible panels, keyboard and swipe control, and an action menu for reset, sharing and Map Only.
- **Map-aware positioning:** selected coordinates are centred in the visible, unobscured map area when the bottom sheet is open.
- **Display preferences** (basemap, embedded-layer visibility, category filters and opacity values) are stored in the browser's local storage when available. GPS location and search history are not persisted by this preference feature; the user can intentionally copy a share URL containing selected coordinates.
- Larger important mobile touch targets, clearer metadata contrast and a visible clear-search button.

## Installation and GitHub Pages

1. Create a **public repository** in your GitHub account (for example, `Noongar-Boodja-Atlas`).
2. Place this ZIP's `index.html`, `README.md`, `LICENSE.md` and `THIRD_PARTY_NOTICES.md` in the repository root.
3. In the repository's **Settings → Pages**, configure **Deploy from a branch**, choosing `main` and `/ (root)`.
4. Open the published URL, normally `https://<username>.github.io/<repository>/`, and test online basemaps and external WMS layers on desktop and mobile.
5. Keep the source attributions and licence documents alongside the HTML.

The embedded geographic calculations and vector fallback work without an external GIS backend, but Leaflet is currently loaded through a CDN. The satellite, terrain and other online map layers require an internet connection. The Atlas is **not** guaranteed to be completely offline-capable.

## Licence and cultural-use conditions

- Atlas-owned original code is offered for noncommercial use under **PolyForm Noncommercial 1.0.0**.
- Atlas-owned original text and copyright-protected compilations are offered under **CC BY-NC 4.0**.
- A separate **Indigenous-controlled organisation permission** is proposed to allow eligible Aboriginal and Torres Strait Islander organisations to use, adapt and redistribute Atlas-owned material, including for their own revenue-generating activities.
- The maintainer confirms permission to **redistribute the original shapefile layer**, but the original rights holder, attribution requirements and any downstream sublicensing/commercial reuse permissions still need to be documented. The Atlas cannot grant rights that its operator does not control.
- Public third-party basemaps, library scripts and WMS services retain their own terms.

See `LICENSE.md` and `THIRD_PARTY_NOTICES.md`. The custom additional permission should be reviewed before public release.

## QA and remaining checks

- The HTML's polygons, places and aliases were checked as **byte-for-byte equivalent JSON records** to the previously delivered Atlas version.
- Spatial tests include Perth, Bunbury, a two-group border, a three-group junction, and **110 additional independent random point-in-polygon tests** against the original shapefile geometry.
- Headless-browser checks cover desktop and multiple mobile viewport sizes (including 320, 375, 390 and 515 CSS px), bottom-sheet states, visible primary results, tooltip/coordinate positioning, panel collapse, basic search and offline vector mode.
- The **Leaflet application hooks**, including the GPS accuracy circle, were tested using a simulated Leaflet environment; this is **not** a substitute for full live browser testing against actual online Geoscience Australia, Esri or WA WMS endpoints. Those remain outstanding before publication.
- Geoapify address results were tested against a **mock service**, not a live API key; live geocoding and provider quota behaviour require testing after configuration. Place-centre coordinates remain approximate, especially for large-area natural features, mines and industrial complexes. They should not be used for heritage clearances or site-level decisions.

The site has **not** been published to any GitHub account by this package.
