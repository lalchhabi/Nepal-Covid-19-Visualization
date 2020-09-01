NepalMaps
---------

[baselayers](https://github.com/anjesh/NepalMaps/tree/master/baselayers/NPL_adm) contains Nepal's administrative boundaries data in shapefile, downloaded from [GADM.org](http://gadm.org). The data is licensed CC-A-3.0 from `FortiusOne Inc. (via WorldBank; http://maps.worldbank.org/overlays/3238) (Creative Commons Attribution 3.0 License.)`.

KML and GeoJSON data are created from the shapefile using ogr2ogr tool. 

The Regions kml and geojson data files are created from NPM_adm2.shp

`ogr2ogr -f "KML" regions.kml baselayers/NPL_adm/NPL_adm1.shp -sql "select NAME_1 as Region from NPL_adm1"`

`ogr2ogr -f "geojson" regions.json baselayers/NPL_adm/NPL_adm1.shp -sql "select NAME_1 as Region from NPL_adm1"`


The Zone kml and geojson data files are created from NPM_adm2.shp

`ogr2ogr -f "KML" zones.kml baselayers/NPL_adm/NPL_adm2.shp -sql "select NAME_1 AS Region, NAME_2 AS Zone from NPL_adm2"`

`ogr2ogr -f "geojson" zones.json baselayers/NPL_adm/NPL_adm2.shp -sql "select NAME_1 AS Region, NAME_2 AS Zone from NPL_adm2"`


The district kml and geojson data files are created from NPM_adm3.shp

`ogr2ogr -f "KML" districts.kml baselayers/NPL_adm/NPL_adm3.shp -sql "select NAME_1 AS Region, NAME_2 AS Zone, NAME_3 as District from NPL_adm3"`

`ogr2ogr -f "geojson" districts.json baselayers/NPL_adm/NPL_adm3.shp -sql "select NAME_1 AS Region, NAME_2 AS Zone, NAME_3 as District from NPL_adm3"`

The VDC kml and geojson data files are created from NPL_adm4.shp file

`ogr2ogr -f "KML" kapilvastu.kml NPL_adm4.shp -sql "select NAME_2 AS ZONE,NAME_3 AS DISTRICT, NAME_4 AS VDC from NPL_adm4 where NAME_3='Kapilbastu'"`

`ogr2ogr -f "GeoJSON" kapilvastu.json NPL_adm4.shp -sql "select NAME_2 AS ZONE,NAME_3 AS DISTRICT, NAME_4 AS VDC from NPL_adm4 where NAME_3=‘Kapilbastu'"`
