# Lighthouse map Sonification
This repository (will) hosts a sonification of the blinking beacon map.

The beacon map shows all the blinking beacons from [OpenStreetMap](https://www.openstreetmap.org/).
![Demo time](https://geodienst.github.io/lighthousemap/demo.gif)
More specifically, it asks the [Overpass API](https://www.overpass-api.de) for all elements with an `seamark:light:sequence` attribute, decodes these, and displays them as coloured circles on the map using [Leaflet](https://leafletjs.com). It also tries to take the `seamark:light:range` and `seamark:light:colour` into account.

## Overpass API
The current version uses an extracted dataset, but the code allows for directly querying the Overpass API. However, since a query like the one used here can take multiple minutes to complete it is not very useful do always do live queries.

## Useful stuff
The `leaflet.indexedfeaturelayer.js` file contains an extension on Leaflet's GeoJSON layer that only add layers/features to the map that are (or are about to be) visible. It uses a spatial index to quickly query which features can be removed from the DOM, increasing performance.

`leaflet.light.js` contains my best guess on how a light sequence will look based on [these descriptions](https://wiki.openstreetmap.org/wiki/Seamarks/Light_Characters). However, it might be inaccurate, and it tries to do its best with the sometimes not entirely consistent data from OSM.

## Credits
This map is made by the [Geodienst](https://www.geodienst.xyz) because it was a fun idea we wanted to try out. Feel free to fork this map and make your own visualisation of OSM data, or contribute improvements back to us. 

# TODO
-API parsing
-web audio api hooks
-basic voices
-note per colour
-pattern sync
-register per size (bigger lower)
-changing mode/chord based on time
-reverb
-modulation
