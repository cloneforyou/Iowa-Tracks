# How to load custom data

1. Fork this project
2. Use [Overpass Turbo](https://overpass-turbo.eu) to search for data. You can type `swimming pool` into the wizard and search across the entire bounding box. Or use the wizard and search `swimming pool in SOMECITYNAME`. The scope of the project is not limited to swimming pool data, so instead you could do something like searching for `amenity=school & building=school`
3. Select export and then download the GeoJSON file
4. Use [Mapshaper](https://mapshaper.org) to convert the GeoJSON file into a TopoJSON file
5. Rename both of the files to pools and overwrite the files in your forked directory
6. Set up a page for the project, utilizing the [GitHub tutorial](https://pages.github.com/)
7. Visit https://YOURNAMEHERE.github.io/swimming-pools/

