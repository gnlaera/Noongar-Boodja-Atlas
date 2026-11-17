# Noongar Boodja | Geographic & Language Atlas

**Release v1.0-rc6.8 · 17 November 2026**

## Key references

The Atlas is a guide only. It does not decide Traditional Ownership, cultural authority, native title, Aboriginal heritage status, legal boundaries or who can speak for Country. It draws on these main references:

- **South West Native Title Settlement:** [About the Settlement Agreement](https://www.noongar.org.au/about-settlement-agreement), South West Aboriginal Land and Sea Council. Background on the Settlement and its six Indigenous Land Use Agreements (ILUAs).
- **ILUA boundaries:** [Native Title (ILUA) (LGATE-067)](https://catalogue.data.wa.gov.au/dataset/native-title-ilua-lgate-067), Landgate, published on data.wa.gov.au. This is the source of the six ILUA extents and the 1,695 vertices in `noongar_iluas_official_vertices.csv`. Use of Landgate data is subject to Landgate's licence terms. Official ILUA records are held on the National Native Title Tribunal (NNTT) register.
- **Background research:** [Atlas research notebook](https://notebook.google.com/notebook/b07170cd-9173-46c6-889b-3ad53c32249c) (Google), shared as a public link. It is a working research aid, not a published source.
- **Further reading:** [Map of Indigenous Australia](https://aiatsis.gov.au/explore/map-indigenous-australia), Australian Institute of Aboriginal and Torres Strait Islander Studies (AIATSIS). A national view of the general locations of larger language, social or nation groupings. AIATSIS states that it is not exact and not suitable for native title or other land claims. **It was not used to draw any area in this Atlas**, and some names and spellings differ. The AIATSIS map may not be reproduced without permission, so the Atlas links to it only.

Other sources are listed in `THIRD_PARTY_NOTICES.md` and, for each place of cultural relevance, in `noongar_places_candidate_register.csv`.

A single-file interactive atlas (`index.html`) for exploring **indicative** Noongar language-group geography in south-western Western Australia. The Atlas is a geographic reference, not a legal or cultural determination of Traditional Ownership, native title, language authority, or Aboriginal heritage status.

## Contents

- **12 language-group polygons**, with 3,418 ring vertices and 3,401 connecting segments, retained from the user-supplied source shapefiles.
- **345 reference locations** (from v1.0-rc6.4; originally **290 curated reference places**), including cities, towns, natural landmarks, heritage sites, industrial facilities and mines. Many are indicative pins rather than surveyed site centres.
- **98 language-name records**, with common, historical and source-map variants, including caution flags for ambiguous names.
- Coordinate lookup, nearest mapped edge distance, on-line group candidates, nearby group boundaries, map filters, share links and CSV exports.
- Address and postcode lookup via optional **Geoapify forward geocoding**, with user-selected candidates displayed as map markers. The key is configured and restricted to the published GitHub Pages site (see below).
- Browser-permitted device geolocation on mobile and desktop, with an indicative reported accuracy radius, visible map centring and language-group classification.
- Three basemaps: Geoscience Australia topographic, Esri terrain/roads and Esri satellite imagery. (WA government WMS overlays were removed in v1.0-rc6.)

## New in version 4

- **Unified search:** The existing search box continues to find all embedded places, Noongar group names/aliases and decimal GPS coordinates without any external service. It also offers an explicit **Find address or postcode** action for online searches. The external query is sent only on user submission, not at every keystroke.
- **Real addresses and postcodes:** Configured Geoapify returns selectable matches for street addresses, suburbs and postcodes within the atlas's south-west WA geographic scope. Postcode results are identified as **area reference points**, not property coordinates. Results are run through the atlas's existing polygon and mapped-boundary calculations.
- **Device location:** Tap **GPS / Use my location** on phone or desktop. The browser asks permission, recentres the map and shows the reported accuracy radius as a circle. Desktop accuracy may be coarse if derived from network/Wi-Fi signals. The device's coordinates are not transmitted to the external geocoder.
- **Map framing:** Existing bottom-sheet-aware placement is retained. The GPS precision automatically selects a suitable zoom level.
- **Privacy and resilience:** Address queries are third-party requests, with the provider identified in About. Embedded places, language groups, map-click lookup and GPS continue to work when no geocoding key is configured or the provider is unavailable.

### Address and postcode search (configured from v1.0-rc6.7)

- `index.html` contains the Atlas's Geoapify browser key (`GEOAPIFY_KEY`). A browser key is always visible in a public web page, so it is protected by restrictions, not secrecy.
- In the Geoapify dashboard the key is restricted to the origin `https://gnlaera.github.io` and the Atlas referrer URLs under `https://gnlaera.github.io/Noongar-Boodja-Atlas/`. Requests from any other site are refused.
- Because of this, **address search does not work when `index.html` is opened from a local folder or another website**. The Atlas then shows a short message; places, language groups, coordinates and GPS still work.
- If the repository or GitHub account name changes, update the allowed origin and referrers in Geoapify first. If the key is ever misused, create a new restricted key and replace it in `index.html`.
- Check usage and quota occasionally in the Geoapify dashboard. Keep Geoapify and OpenStreetMap attribution visible.

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
4. Open the published URL, normally `https://<username>.github.io/<repository>/`, and test online basemaps and address search on desktop and mobile.
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

## v1.0-rc6 stabilisation and consolidation

This release keeps the single-file `index.html` deployment model while reorganising the file with clearer section comments and consolidated defaults.

Key changes:

- 36 public-source places are integrated into the normal Locations catalogue under `Place of cultural relevance`.
- All 36 are displayed and searchable by display name, alternate name, category and place type.
- Selecting a place of cultural relevance shows its public source, publisher, coordinate quality and limitation.
- The public points are orientation references, not Aboriginal heritage-site boundaries and not determinations of cultural authority.
- Basemap opacity defaults to 100%, language-group fill to 22%, language-group boundaries to 70%, ILUA boundaries to 80%, labels to 100%, and location markers to 85%.
- Language-group and ILUA labels use opaque text boxes. From v1.0-rc6.5 they are styled differently: see the v1.0-rc6.5 notes below.
- Government Web Map Service overlays and selectors are removed.
- Keyboard focus indicators and an accessible map-region label are included.

### v1.0-rc6.4 changes

- **Label colours:** label borders take the polygon colour. Label text uses a darker shade of the same colour, with at least 4.5:1 contrast.
- **21 Wagyl register places added** (WAG-001 to WAG-021) as "Place of cultural relevance" (Atlas IDs 325 to 345). Total locations: 345. Places of cultural relevance: 57. These records have **no public URL**. They show "no public URL recorded", "Not reviewed" and "Conditional - cultural review required".
- **Fix:** places of cultural relevance now draw on the map. In rc6.3 the category was missing from the category list.
- **Fix:** evidence panels no longer stack or persist after another selection.
- **Fix:** the polygon fill readout shows the real default (22%).
- **Data:** places of cultural relevance now have their language-group (`inside`) values, so group filters and counts include them.
- **Register CSV:** `noongar_places_candidate_register.csv` holds all 57 records, with new `Alternate_Names`, `Region_Named_In_Source` and `Atlas_ID` columns.

### v1.0-rc6.5 changes

- **Compact header:** reduced from 68 px to 48 px.
- **Quick views:** All layers, Language groups, ILUAs and Wagyl places. On screens 860 px wide or narrower they are in the ⋯ menu. Any manual layer change, or Restore default layers, clears the quick view.
- **ILUAs are lines only:** a dark solid casing under a bright dotted line in each ILUA's colour (Yued #FF3D9A, Whadjuk People #FFD60A, Ballardong People #22D3EE, Gnaala Karla Booja #FF7A1A, South West Boojarah #A3E635, Wagyl Kaip & Southern Noongar #C084FC).
- **Label styles carry the meaning:** language groups in *italic*; ILUAs in **BOLD CAPITALS** in a dark box. A key explains this in the Layers panel and the Language-group key.
- **"South West Boojarah":** the "#2" was removed everywhere, including `noongar_iluas_official_vertices.csv`. The NNTT register lists the agreement as "South West Boojarah #2"; match records by NNTT ID WI2017/013.
- **Preferences:** storage key `noongar-atlas-view-v10`; v9 and v8 settings are migrated once.

### v1.0-rc6.6 changes

- The "About this indicative map" panel is now **About this map and its sources**, in plain English, with links to the key references. Collapsed by default; its text scrolls inside the panel if space is short.
- The About panel and the Language-group key open one at a time.
- README: new **Key references** section.

### v1.0-rc6.7 changes

- **AIATSIS Map of Indigenous Australia** added as further reading in the About panel, the About tab and the README, with AIATSIS's own caution. It is linked, not reproduced, and was not used to draw any area.
- **Research notebook:** the "you may need to sign in" note was removed; the link is a public share link.
- **Address and postcode search is switched on** with the origin-restricted Geoapify key. A refused request (for example from a local copy) shows a plain message instead of an HTTP error.
- **About tab clean-up:** removed four source links for the government map layers deleted in rc6 (DBCA reserves, MINEDEX, hydrography, Ramsar wetlands) and added the four key references. Fixed the broken LICENSE and third-party notice links (they pointed to a misspelt folder); they now open the files on GitHub.

### v1.0-rc6.8 changes

- **Fix: locations could not be clicked on the online map.** A transparent ILUA drawing layer sat above the location markers and caught every click, so clicking a dot selected a bare coordinate instead of the place. Location markers now sit in their own top layer.
- **Bigger click targets.** Each marker has a 26 px click area (34 px on touch screens), even though the symbol itself is smaller. A click or tap within 16 px (22 px on touch) of a visible location selects that location. Where symbols overlap, the one nearest the pointer is chosen.
- **Wagyl places quick view** shows its symbols about a third larger.
- **Marker symbols by category** (shape and colour, so meaning does not rely on colour alone): City / major centre = square; Town / locality = small dot; Natural feature = triangle; Historic / heritage = diamond; Industrial / infrastructure = hexagon; Mine / extractive = cross; Place of cultural relevance = ring. The symbols appear in the Layers panel, the Places list and the offline map. Hovering a symbol shows its name.
- **Selected place** is marked with an orange ring that never blocks clicks.
- **Fix (offline map):** clicking a location symbol on the offline vector map now selects that place.
