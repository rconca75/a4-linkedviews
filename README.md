# A4: Brushing and Linked Views

*Site Link: https://rconca75.github.io/a4-linkedviews/*

## Intro

For this assignment, I chose to make visualizations of COVID-19 data I found on a Geeks for Geeks page (Disclaimer: I have no idea how accurate this dataset is nor when it's from, I just wanted something with minimal data cleaning, so take this with a grain of salt). The dataset contains different statistics about COVID-19 from different countries, such as confirmed cases, the total number of recoveries/deaths, currently active cases, and other information for 187 total countries.

For this project, I decided to focus on four main attributes: confirmed cases, active cases, recovered cases, and deaths since I felt those were what people would be most interested in.

## Visualization 1: Scatterplot

For the first visualization, I chose to make a scatterplot. The plot takes input from the CSV file and plots it on a graph using Active cases as the X value and Recovered cases as the Y value. This allows viewers to see correlation between how many cases are currently ongoing in each country versus how well the country is taking care of their sick. The data points are scaled by the amount of confirmed cases in the country (the bigger the point, the more cases were confirmed in that country). Ideally, you would want your country to be as close to the axis as possible, or close to the Y-axis, indicating less active cases within your country.

Once I added the size scaling, it showed trends where the smaller points tended to be closer to the origin, while points further away tended to be much larger which makes sense considering you would need more confirmed cases to have more active/recovered cases.

I also colored the points based on the WHO region to possibly identify trends that emerged within the different regions of the world.

To give users more control and ability to explore the data, I added a zoom feature to the graph so that users can move through the data rather than just looking at it in one view since there are some smaller points that are harder to see and some larger ones that wouldn't really fit on the graph without making very drastic changes to the scaling.

Lastly, I added a tooltip that displays the name and WHO region of the country whenever the viewer hovers their mouse over a point so that it would be easy to tell what data belongs to which country. The tooltip also updates the style of the point to be opaque (they're normally set to 0.8 opacity) and outlines the point to make it clear what point the user is hovering over.

## Visualization 2: Bar Chart

The next visualization I decided to make was a bar chart that expanded upon the individual details/statistics of each country. This bar chart links to the scatterplot such that it only shows data from the country being hovered over on the scatterplot.

The bar chart contains details about the number of active cases, recovered cases, deaths, and total confirmed cases for a single country. This gives more insight into the specific details of the country in a way that may be easier to comprehend than the scatterplot alone.

Since the axis of the bar chart automatically updates based on the max value in all four columns (usually confirmed cases), I added a tooltip that tells you the exact value of each column when hovering over that column and changes the color/outline of the bar as well.

## Final Product Screenshot

![Screenshot](vis_screenshot.png)

## Technical Achievements

Each visualization is interactive for the viewer, mostly via a tooltip to give more information about the point/bar. These automatically populate with data directly from the CSV file.

Additionally, the scatterplot has zoom/panning functionality, allowing users more freedom to explore the data and increasing the functionality of the tooltip since they don't usually work as well with clustered data.

The scatterplot and bar chart are linked together, with the bar chart only populating with data from the scatterplot the user is actively hovering over.

## Design Achievements

Both visualizations are easy to read with relevant axis labelling and tooltip labelling that help give context to what the viewer is looking at. The colors on the scatterplot are determined by region, meaning all countries in the same region have the same coloring.

The interactivity components with `moveover`, `mousemove`, and `mouseleave` functions change the opacity and stroke, making it clear what point a user is currently viewing the data of.

Additionally, the zoom feature on the scatterplot makes the tooltip function pretty well, which was an issue I ran into on A2 where my tooltip didn't function very well in crowded areas.

## Note:

The zoom function works only when you currently aren't hovering over a point. This usually isn't an issue, but some of the points are so absurdly large they take up the whole screen (namely the US point) so just be aware if you zoom a certain way you may need to reload the site.