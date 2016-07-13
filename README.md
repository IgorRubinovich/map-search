##&lt;map-search&gt;

`map-search` utilizes the Google Maps API and Polymer paper elements to create a map with search functionality. The map displays points of interest with markers generated by taking in data containing at minimum a latitude and longitude alond with other marker options (as described in Google's API reference) or additional properties.

Example in html:

```html
<map-search></map-search>
```

The following properties can be changed by the user as needed:

| Custom property | Description | Default |
| --- | --- | --- |
| `defaultCenter` | The default center of the map upon loading | Prague: `{ lat:50.0755, lng:14.4378 }`|
| `defaultMapOptions` | The default load of the map | `{ zoom: 17, mapTypeId: google.maps.MapTypeId.ROADMAP }`|
| `onePolyActive` | If true, beginning to draw a new poly will erase previous polys | `true` |
| `dataServer` | The url from which to pull marker data | `http://localhost:4000` |
| `defaultIcon` | Default icon to switch to for a selected marker | `http://46.101.211.226:5000/media/assets/theme-vinegret/logo-vinegret-mobile.png` |
| `percentMinimize` | The percentage of current window height to minimze to| `0.5` |


The following is a description of all public functions:

| Public function | Description |
| --- | --- |
| `loadFromServer` | Generates a request from the url specified in `dataServer` |
| `itemsLoaded` | Called when request is finished, builds markers from data in response |
| `newMarker` | Creates a new marker from an object or array of objects containing marker options and adds it to the map |
| `draw` | Allows user to draw maps polygons by freehand. All current markers and all new markers loaded inside shap are marked as selected|
| `clear` | Clears away all poly shapes if any are on the map. If not, all markers are deselected |
| `filter` | Removes all unselected markers from map |
| `reload` | Restores map with all past loaded markers marked unselected |
| `minimize` | Minimizes the map height as specified by `percentMinimize` |
| `collapse` | Collapses the map so the element only displays the toolbar |
