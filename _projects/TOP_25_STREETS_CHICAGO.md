---
name: Final - Top 25 Streets with crash in Chicago
tools: [Python, HTML, vega-lite]
image: assets/pngs/final.png
description: Top 25 Streets by Number of Crashes in Chicago from January 2024 to April 2025 broken down by Day of the Week and type of injuries
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Use of the Graphs and Charts

The charts and graphs on this page show what streets have the most crashes and injuries per day of the week. This is useful for figuring out when and where, season and weather independent, crashes are in Chicago, IL in 2024 and early 2025. Moreover, the map section shows the general area where crashes happen in Chicago. These data visualizations are most useful to residents of Chicago and people familiar with its geography.


# Graphs of Top 25 streets by Total Number of Crashes broken out by day of the week and injuries sustained

Select a street in the drop down. that will update the charts and map to the street selected. By default the charts show the grand totals of crahes and injuries. Mouse over the bars in the charts to see totals for each segement.

<vegachart schema-url="{{ site.baseurl }}/assets/json/final5.json" style="width: 100%"></vegachart>

# Top 25 Streets Sorted by Total Number of Crashes

Below is a table of the data breakdown sorted by total number of crashes per street. This is the basis for graphs above. A missing component is the day of the week calculations. Present is that there is a noticeable and direct correlation between number of crashes and number of injuries.

<table>
  {% for row in site.data.top_25 %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>


# Disclaimer from City of Chicago

This site provides applications using data that has been modified for use from its original source, www.cityofchicago.org, the official website of the City of Chicago.  The City of Chicago makes no claims as to the content, accuracy, timeliness, or completeness of any of the data provided at this site.  The data provided at this site is subject to change at any time.  It is understood that the data provided at this site is being used at one’s own risk.

<!--
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
<!--
<div class="left">
{% include elements/button.html link="https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if/explore/query/SELECT%0A%20%20%60crash_record_id%60%2C%0A%20%20%60crash_date_est_i%60%2C%0A%20%20%60crash_date%60%2C%0A%20%20%60posted_speed_limit%60%2C%0A%20%20%60traffic_control_device%60%2C%0A%20%20%60device_condition%60%2C%0A%20%20%60weather_condition%60%2C%0A%20%20%60lighting_condition%60%2C%0A%20%20%60first_crash_type%60%2C%0A%20%20%60trafficway_type%60%2C%0A%20%20%60lane_cnt%60%2C%0A%20%20%60alignment%60%2C%0A%20%20%60roadway_surface_cond%60%2C%0A%20%20%60road_defect%60%2C%0A%20%20%60report_type%60%2C%0A%20%20%60crash_type%60%2C%0A%20%20%60intersection_related_i%60%2C%0A%20%20%60private_property_i%60%2C%0A%20%20%60hit_and_run_i%60%2C%0A%20%20%60damage%60%2C%0A%20%20%60date_police_notified%60%2C%0A%20%20%60prim_contributory_cause%60%2C%0A%20%20%60sec_contributory_cause%60%2C%0A%20%20%60street_no%60%2C%0A%20%20%60street_direction%60%2C%0A%20%20%60street_name%60%2C%0A%20%20%60beat_of_occurrence%60%2C%0A%20%20%60photos_taken_i%60%2C%0A%20%20%60statements_taken_i%60%2C%0A%20%20%60dooring_i%60%2C%0A%20%20%60work_zone_i%60%2C%0A%20%20%60work_zone_type%60%2C%0A%20%20%60workers_present_i%60%2C%0A%20%20%60num_units%60%2C%0A%20%20%60most_severe_injury%60%2C%0A%20%20%60injuries_total%60%2C%0A%20%20%60injuries_fatal%60%2C%0A%20%20%60injuries_incapacitating%60%2C%0A%20%20%60injuries_non_incapacitating%60%2C%0A%20%20%60injuries_reported_not_evident%60%2C%0A%20%20%60injuries_no_indication%60%2C%0A%20%20%60injuries_unknown%60%2C%0A%20%20%60crash_hour%60%2C%0A%20%20%60crash_day_of_week%60%2C%0A%20%20%60crash_month%60%2C%0A%20%20%60latitude%60%2C%0A%20%20%60longitude%60%2C%0A%20%20%60location%60%0AWHERE%0A%20%20%60crash_date%60%0A%20%20%20%20BETWEEN%20%222024-01-01T00%3A00%3A00%22%20%3A%3A%20floating_timestamp%0A%20%20%20%20AND%20%222025-04-13T11%3A48%3A27%22%20%3A%3A%20floating_timestamp%0AORDER%20BY%20%60crash_date%60%20DESC%20NULL%20FIRST%2C%20%60crash_record_id%60%20ASC%20NULL%20LAST/page/filter" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/np42-uiuc/np42-uiuc.github.io/blob/2826b559ffc560867f63acae3c63e9f1fbcdd0f4/python_notebooks/Workbook.ipynb" text="The Analysis" %}
</div>
--->
