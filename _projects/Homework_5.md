---
name: Home Work Five - Big Foot
tools: [Python, HTML, vega-lite]
image: assets/pngs/bf_year_state_chart.png
description: Comparison of Big Foot Sightings by Year and By State
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Date Range as Area and Slider


<vegachart schema-url="{{ site.baseurl }}/assets/json/bf_daterange_chart.json" style="width: 100%"></vegachart>

This chart is a display of the number of sightings over time with the ability to zoom into specific ranges. The main interactivity is the scrubbing and selecting in lower portion of the graph. The specific choice made was the chart type as an area chart instead of a bar chart or histogram. The main reason for the area chart is that I’m looking at the change over time. The area chart provides a greater understanding with the zoom selection. The shape is defined by a count of year and breaking down further by state or weather condition did not add to the story.

# States with Sitting per year

<vegachart schema-url="{{ site.baseurl }}/assets/json/bf_year_state_chart.json" style="width: 100%"></vegachart>

This chart displays total sightings per year as well as total sightings by state. The total sightings by state portion is also interactive. Clicking on a state’s column will change the sightings per year to focus on that state. The color and encoding is default. The default schema to break down by states had too few options for all the states. Moreover, the goal of the chart is to show the number of sightings per state. The interactivity of the sightings per year updating to the specific state. Breaking out the sightings by year allows for context for why Wyoming has the most sightings but it’s a gentle slope instead of a spike.


## Search The Data & Methods

<!--Below is where we can put some links to both the data and the analysis code as buttons:

```
<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://blog.4dcu.be/programming/2021/05/03/Interactive-Visualizations.html" text="The Analysis" %}
</div>
```
--->

<!-- these are written in a combo of html and liquid -->

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>
