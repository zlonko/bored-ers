# bored-ers
Making maps is fun, but sometimes the pre-processing stuff is not. This is a collection of odds and ends I've come across when putting together geographic visuals. Hopefully they can save you a little time.

## Boundaries

These common boundary sets for the United States:

1. U.S. States
2. U.S. Counties (simplified)
3. U.S. Census Tracts (simplified)
4. U.S. Congressional Districts (ugh) (working to add these)
5. U.S. Zip Code Tabulation Areas (VERY ugh)
6. The Whole Outline of the United States™

In past projects, I have encountered difficulties using these same data from open-source repositories, but I neither documented those difficulties nor took the time to create a reliable toolkit. Consequently, I have lost time to scavenging for a specific dataset or re-scoping data from previous projects... I think this is not uncommon in the world of data viz 😅. Some example issues, which I've tried to ameliorate:

- "Rewinding" the order of polygons in JSON, so that it could be visualized with D3. That's a hassle. You can read about it here: [link](https://stackoverflow.com/questions/54947126/geojson-map-with-d3-only-rendering-a-single-path-in-a-feature-collection).

- Reducing the size of most raw GeoJSON returned from databases. This can be done with MapShaper (an excellent tool!) but again it is an extra step.

- Needing datasets in niche scopes, such as all of the census tracts in Arkansas, etc. You can do this by filtering a larger JSON file, but it can be faster and lighter to have an "out-of-the-box" option.

## Common Data

1. Common naming schemes from the U.S. Census, etc., like converting FIPS to state names.
2. The common name locations of ZCTA codes. Like ZIP codes, ZCTA don't really belong to counties, but both are casually discussed as "within" counties. So, in case you need to roughly associate ZCTA data with counties.
3. State dimensions: the length and width of states, their centroids, and the coordinates of their bounding box vertices.These data are not complex to calculate, but here they are so that no person must.