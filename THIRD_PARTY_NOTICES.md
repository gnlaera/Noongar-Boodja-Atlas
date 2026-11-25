# Third-party notices and dataset rights

This registry distinguishes Atlas-original work from separate content and service providers. It is not a blanket licence to copy third-party maps or geographic layers.

| Resource | How the Atlas uses it | Licence / terms to check |
|---|---|---|
| Leaflet 1.9.4 | Mapping JavaScript and CSS loaded via CDN | [BSD 2-Clause](https://github.com/Leaflet/Leaflet/blob/v1.9.4/LICENSE) and retain library attribution |
| OpenStreetMap | Underlying names, contributed cartography and relevant Geoapify-geocoder source data | [Copyright and ODbL](https://www.openstreetmap.org/copyright); [tile use policy](https://operations.osmfoundation.org/policies/tiles/) |
| Geoscience Australia | National basemap services | [Geoscience Australia mapping services](https://services.ga.gov.au/gis/rest/services); attribution and source-specific terms |
| Esri | Optional imagery / reference basemaps | [Esri attribution requirements](https://developers.arcgis.com/documentation/esri-and-data-attribution/); access and tile-use conditions |
| Western Australia SLIP public GIS services | Not used since v1.0-rc6 (government map layers removed) | Check the applicable dataset metadata and licence individually through the [WA Data Catalogue](https://catalogue.data.wa.gov.au/) and service provider |
| Geoapify | Optional online address/postcode geocoding on explicit user searches | [Geoapify Geocoding API and terms](https://apidocs.geoapify.com/docs/geocoding/); a free, origin-restricted API key is needed. Attribution to Geoapify and applicable OpenStreetMap data sources; geocoding and user queries may be processed by Geoapify. |
| Original language-group shapefiles | The embedded 12 indicative language-group polygons and rings | **Redistribution permission reported by Atlas operator.** Original rightsholder, attribution and downstream sublicensing rights need documenting. |
| Curated places and aliases | Atlas-original arrangement and original explanatory notes, where protected | CC BY-NC 4.0 plus alternative Indigenous community permission in [LICENSE.md](LICENSE.md), **excluding any third-party records subject to their own terms** |

**WBE reference:** the World Bathymetry Explorer provided design inspiration, not a licence for wholesale copying of GPL-licensed source code. The Atlas code should remain independently written; review provenance before including any WBE code, since GNU GPL derivative obligations cannot be overridden with a commercial-use ban.

**Data governance:** publishing a layer with permission is not the same as having the right to issue downstream commercial or noncommercial licences to its constituent geographic records. Confirm that any language-group data permission covers the specific public repository and use by Indigenous organisations envisaged here.

## Historical v1.0-rc6 cultural-reference release note (superseded by v1.1.0)

The Atlas integrates 36 public representative points into the main Locations catalogue. Source references are drawn from public materials published by the Department of Biodiversity, Conservation and Attractions, City of Fremantle, City of Bunbury and City of Albany. Each record identifies its source and carries a limitation stating that the point is not a cultural-site boundary and does not determine cultural authority. Public-source inclusion does not replace review by the relevant Noongar cultural authority.

### Historical v1.0-rc6.4 supplied Wagyl-register release note

The internal candidate register includes 21 records (WAG-001 to WAG-021) from a supplied Wagyl geolocated register. These were displayed publicly in v1.0-rc6.4 but are not published wholesale in v1.1.0. The register lists compiled references, including internal compilations, reports and some Wikipedia pages. It does not record a publisher or public URL. These records are labelled "Supplied register - not publicly verified" and have not been reviewed by the relevant Noongar cultural authority. Rights in the underlying cultural knowledge stay with the relevant Noongar people and are not relicensed by the Atlas.

### v1.0-rc6.5 ILUA naming

ILUA display names are shortened for readability. "South West Boojarah #2" is shown as "South West Boojarah". Official register entries should be matched by NNTT ID (e.g. WI2017/013).

### v1.0-rc6.7 references and services

- **AIATSIS Map of Indigenous Australia** (David R Horton, © AIATSIS 1996): linked as further reading only. No AIATSIS map content is reproduced, and AIATSIS does not permit reproduction without permission.
- **Western Australia SLIP public GIS services:** no longer used. The government map layers were removed in v1.0-rc6.
- **Geoapify:** address and postcode search is now active, using a public browser key restricted to `https://gnlaera.github.io`. Search text is sent to Geoapify only when a user chooses the online address search.

### v1.0-rc6.9 header artwork

`noongar-boodja-atlas.jpg` and the small copy embedded in `index.html` were generated with an AI image tool by the project maintainer for this side project, and approved for use in the Atlas by GKB staff. The artwork is decorative. It is not a map, does not show real boundaries or sites, and is not the work of a named Aboriginal artist. Do not reuse it outside the Atlas without checking with GKB.


### v1.1.0 cultural-reference and Wagyl evidence audit

The supplied 21-record Wagyl register is retained as an internal research and audit trail, but it is no longer published wholesale. Public display requires an identifiable source supporting the specific public claim. AI-generated syntheses, Wikipedia-style drafts and unattributed compilations are discovery leads only, not final cultural authority.

The public Atlas currently retains:
- **WAG-011**, reframed as the Mandurah estuary and connected waterways, with an attributable account by Franklyn Nannup in *Barragup Yarns*;
- **WAG-004**, Derbal Yarrigan / Swan River, as a cultural reference place without an explicit Wagyl claim in the cited passage; and
- **WAG-013**, Korijekup / Harvey and surrounding Bindjareb Country, as a community-led cultural reference place without an explicit Wagyl claim in the original project page.

WAG-012 is merged into WAG-011. Other supplied-register records remain internal candidates pending suitable evidence and review. Public citation does not transfer copyright or cultural authority.
