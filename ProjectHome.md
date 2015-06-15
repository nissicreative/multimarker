Adding thousands of GMarker objects or google.maps.Marker objects to a map can be very slow.  Redfin Multimarker is the fastest way to add hundreds of markers to a Google map.

| |V2 Gmarker|V2 MarkerLight|V3 Gmarker|V3 MultiMarker|
|:|:---------|:-------------|:---------|:-------------|
|IE6|44 seconds|9.0 seconds   |56 seconds|1.5s          |
|IE7|42 seconds|6 seconds     |3.5 seconds|1s            |
|IE8|32 seconds|3.1 seconds   |1.5 seconds|<1s           |
|IE9|3 seconds |0.9 seconds   |<1s       |<1s           |
|FF4|5.1 seconds|1.2 seconds   |<1s       |<1s           |
|GC10|2.4 seconds|<1s           |<1s       |<1s           |
|iPhone 4|40 seconds|6 seconds     |3 seconds |2 seconds     |

(Timed with stopwatch)

Try it for yourself!

[V2 Maps](http://multimarker.googlecode.com/svn/trunk/fast-marker-overlay/maps-v2/example/comparison-test.html)
[V3 Maps](http://multimarker.googlecode.com/svn/trunk/fast-marker-overlay/maps-v3/example/comparison-test.html)

Use it like this in V3:
```
var markers = [];
// id, latLng, innerHtmlArray, divClassName, zIndex, leftOffset, topOffset
var marker = new com.redfin.FastMarker(id, latlng, ["<img src='marker.gif'>"], "myMarker", 0, 10/*px*/, 10/*px*/);
markers.push(marker);
new com.redfin.FastMarkerOverlay(map, fastMarkers);
```

Or like this in V2:
```
var markers = [];
// id, latLng, innerHtmlArray, divClassName, zIndex, leftOffset, topOffset
var marker = new com.redfin.FastMarker(id, latlng, ["<img src='marker.gif'>"], "myMarker", 0, 10/*px*/, 10/*px*/);
markers.push(marker);
map.addOverlay(new com.redfin.FastMarkerOverlay(markers));
```

[Read More](http://blog.redfin.com/devblog/2010/07/introducing_multimarker_the_fastest_way_to_add_many_hundreds_or_thousands_of_markers_on_google_maps.html)