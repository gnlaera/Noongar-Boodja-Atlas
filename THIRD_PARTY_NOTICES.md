# Third-party notices and dataset rights

This registry distinguishes Atlas-original work from separate content and service providers. It is not a blanket licence to copy third-party maps or geographic layers.

| Resource | How the Atlas uses it | Licence / terms to check |
|---|---|---|
| Leaflet 1.9.4 | Mapping JavaScript and CSS loaded via CDN | [BSD 2-Clause](https://github.com/Leaflet/Leaflet/blob/v1.9.4/LICENSE) and retain library attribution |
| OpenStreetMap | Underlying names, contributed cartography and relevant Geoapify-geocoder source data | [Copyright and ODbL](https://www.openstreetmap.org/copyright); [tile use policy](https://operations.osmfoundation.org/policies/tiles/) |
| Geoscience Australia | National basemap services | [Geoscience Australia mapping services](https://services.ga.gov.au/gis/rest/services); attribution and source-specific terms |
| Esri | Optional imagery / reference basemaps | [Esri attribution requirements](https://developers.arcgis.com/documentation/esri-and-data-attribution/); access and tile-use conditions |
| Western Australia SLIP public GIS services | Rivers, conservation, MINEDEX, wetlands or mining layers when enabled | Check the applicable dataset metadata and licence individually through the [WA Data Catalogue](https://catalogue.data.wa.gov.au/) and service provider |
| Geoapify | Optional online address/postcode geocoding on explicit user searches | [Geoapify Geocoding API and terms](https://apidocs.geoapify.com/docs/geocoding/); a free, origin-restricted API key is needed. Attribution to Geoapify and applicable OpenStreetMap data sources; geocoding and user queries may be processed by Geoapify. |
| Original language-group shapefiles | The embedded 12 indicative language-group polygons and rings | **Redistribution permission reported by Atlas operator.** Original rightsholder, attribution and downstream sublicensing rights need documenting. |
| Curated places and aliases | Atlas-original arrangement and original explanatory notes, where protected | CC BY-NC 4.0 plus alternative Indigenous community permission in [LICENSE.md](LICENSE.md), **excluding any third-party records subject to their own terms** |

**WBE reference:** the World Bathymetry Explorer provided design inspiration, not a licence for wholesale copying of GPL-licensed source code. The Atlas code should remain independently written; review provenance before including any WBE code, since GNU GPL derivative obligations cannot be overridden with a commercial-use ban.

**Data governance:** publishing a layer with permission is not the same as having the right to issue downstream commercial or noncommercial licences to its constituent geographic records. Confirm that any language-group data permission covers the specific public repository and use by Indigenous organisations envisaged here.

## Indicative ILUA framing dataset

The Atlas embeds 43 approximate reference vertices from `noongar_iluas_bounding_coordinates.csv` to draw six simplified ILUA frames. The CSV records ILUA names, National Native Title Tribunal identifiers, regional corporation names, ordered reference points and approximate locations. These points do not establish the registered legal boundaries. The resulting frames are orientation aids only and must not be used for legal, tenure, heritage or operational decisions.
