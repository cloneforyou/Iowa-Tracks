# How to load custom data

1. Add data to [OpenStreetMap](https://www.openstreetmap.org)
2. Fork this project
3. Use [Overpass Turbo](https://overpass-turbo.eu) to search for data. For this example, 
```
[out:json][timeout:25];
{{geocodeArea:iowa}}->.searchArea;
(
  relation["leisure"="track"]["sport"="athletics"]["athletics"!~".*"](area.searchArea);
  relation["leisure"="track"]["sport"="running"]["athletics"!~".*"](area.searchArea);
);

out body;
>;
out skel qt;
```
3. Select export and then download the GeoJSON file
4. Use [Mapshaper](https://mapshaper.org) to convert the GeoJSON file into a TopoJSON file
5. Rename both of the files to pools and overwrite the files in your forked directory
6. Set up a page for the project, utilizing the [GitHub tutorial](https://pages.github.com/)
7. Visit https://YOURNAMEHERE.github.io/REPOSITORYNAME/

# Data assumptions

* Not all objects have a `surface=*` tag. The rendering will be based on
  * No `surface=*` = tan
  * `surface=concrete` or `surface=asphalt` = grey
  * `surface=tartan` = ?color?
* Rubberized tracks will be tagged `surface=tartan` and have a `colour=*`
  * `colour=*` will neatly map onto an html colour
  * If `colour=navy` color is remapped to blue
  * If `colour=*` is not specified, it will default to black
* All tracks will be mapped as inner/outer relations. Tracks mapped as ways and more complicated relations will cause errors.
