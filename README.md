# GeoJSON
ABAP Classes to create GeoJSON strings according to [RFC 7946](https://tools.ietf.org/html/rfc7946) and display results with [LeafletJS](https://leafletjs.com).

## Installation
Import Source with [abapGit](https://github.com/larshp/abapGit)

## Usage
This example will create a simple point object:
```
    DATA(geojson) = NEW zcl_geojson( ).
    DATA(point) = geojson->get_new_point(
      i_latitude = CONV #( '49.29278417339369' )
      i_longitude = CONV #( '8.64398717880249' )
    ).
    geojson->add_feature( point ).
    cl_demo_output=>display_json( geojson->get_json( ) ).
```
Result
```
{
 "type":"FeatureCollection",
 "features":
 [
  {
   "type":"Feature",
   "properties":
   {
    "popupContent":""
   },
   "geometry":
   {
    "type":"Point",
    "coordinates":
    [
     8.6439871788025,
     49.2927841733937
    ]
   }
  }
 ]
}
```

More examples: see demo report ZGEOJSON_DEMO

![Result](GeoJSON.PNG "Result")

## License
This software is published under [MIT License](https://github.com/se38/GeoJson/blob/master/LICENSE)
