# sjcMap-android
An example Android app showing how Mapbox-GL-Native can work with ArcGIS Server basemaps. 

## How does it work?
Layers in Mapbox-GL are defined using the [Mapbox GL Style Spec](https://www.mapbox.com/mapbox-gl-style-spec/). The [Sources](https://www.mapbox.com/mapbox-gl-style-spec/#sources) in the Mapbox GL Style specification are defined using the [TileJSON Specification](https://github.com/mapbox/tilejson-spec). 

An ArcGIS Server map service can be referenced in the TileJSON spec provided all the following are true:

1) The map service uses the WGS 1984 Web Mercator (Auxiliary Sphere) projection.

2) The map service has been cached using the ArcGIS Online / Bing Maps / Google Maps tiling scheme.

3) The map service is publically accessible.

See [this file](https://github.com/npeihl/sjcMap-android/blob/master/app/src/main/assets/sjc-imagery.json) that uses the template below to reference a properly configured ArcGIS Server map service.

```
...
"myTiledBasemap": {
  "type": "raster",
  "tiles": [
    "http://example.com/arcgis/rest/services/MyTiledMapService/MapServer/tile/{z}/{y}/{x}"
  ]
}
...
```

## Try it yourself

1) Import this repository into Android Studio.

2) Add your own Mapbox API token in the `strings.xml` file [here](https://github.com/npeihl/sjcMap-android/blob/master/app/src/main/res/values/strings.xml#L6).

3) (Optional) Replace the URL in [this line](https://github.com/npeihl/sjcMap-android/blob/master/app/src/main/assets/sjc-imagery.json#L9) with the URL to your own map service.

4) Run the app using a connected Android device or in an emulator in Android Studio.

## Problems with this example?

- Review the [First steps with the Android SDK](https://www.mapbox.com/help/first-steps-android-sdk/).
- Contact [Mapbox Support](https://www.mapbox.com/contact/)
- [Create a new issue](https://github.com/npeihl/sjcMap-android/issues/new) for this repository. I'll try to help best I can.
