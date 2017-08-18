# Assessing impacts of the upcoming L-train closure

An analysis of the relative impacts for Brooklyn-Manhattan commuters along the section of the L-train scheduled to close for repairs beginning in January, 2019. We use walking distance isochrones from subway stations to identify potentially affected areas, and calculate an approximate average travel time increase for commuters by census tract.

![Alt text](/Data/percentchange_tight.png)

The primary processing and analysis steps are in `main.ipynb`

### Project Outline 
1. Use ![Mapzen isochrone service](https://mapzen.com/documentation/mobility/isochrone/api-reference/) to identify census tracts with centroids with 15 minute walking distance of L-train stations that will be closed.
2. Collect ![LEHD Origin-Destination Employment Statistics data](https://lehd.ces.census.gov/data/lodes/) for the census tracts in the affected area, which provides workplace destination census blocks/tracts for commuters in each origin census block.
3. Use Mapzen Turn-by-Turn API to iteratively calculate travel time differences, for travel with and without the L (see ![transit costing options](https://mapzen.com/documentation/mobility/turn-by-turn/api-reference/#transit-costing-options), from each origin tract to top Manhattan destinations listed for that tract in LODES.
4. Use Shapely to convert decoded geometries to Shapely objects for plotting in Python.
5. Populate a Pandas dataframe with the queried, decoded, and formatted data, for analysis and plotting.

More info...

The L-train (14th Street-Canarsie Local) of the New York City Subway is slated to be shut down in early 2019 for a period of 18 months in order to fix damage incurred during Hurricane Sandy. The closure of this line will significantly impact commuters and other riders of the L, who will need to find alternate transportation services. It will also affect businesses
positioned at or near L-train stops and overall economic development in neighbourhoods served by the line. In order to mitigate the adverse effects of the closure on citizens, the city needs to plan appropriate changes to other transit services.

Increased bus service, using a combination of new routing and additional vehicles, will be needed to compensate for the L-train closure, particularly in less transit-dense areas of Brooklyn.

### Project Flow Diagrams
![Alt text](/Data/Diagram1.png?raw=true )
![Alt text](/Data/Diagram2.png?raw=true )
![Alt text](/Data/Diagram3.png?raw=true )
![Alt text](/Data/Diagram4.png?raw=true )
