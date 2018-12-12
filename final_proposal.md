---
title: Final Project Proposal
feature_image: ""
feature_text: |
  <font size="7" color='black'><span style="background-color: #FDFDFD"> </span></font><br>
  <font size="4" color='black'><span style="background-color: #FDFDFD"> </span></font>
  
---

For this project, I will be analyzing annual water flows for rivers and streams in the Yellowstone National Park Area.  I want to figure out if catchment area size affects the rate of snowmelt discharge through streams in the Yellowstone Area.  To do this I will first use SQL to select USGS Stream Gages that within a 10 mile buffer zone of Yellowstone.  Next I will download data from USGS's website and use python to find the max and min disharge values for specific streams and match that to the Gages around Yellowstone.  Using Python, I will create a script to match the max and min values to their respective Gages and update the attribute table.  

My data will come from [DEM of Yellowstone Area](https://viewer.nationalmap.gov/basic/?category=ned#productGroupSearch), [Stream Polyon](http://download.geofabrik.de/north-america.html), [Polygon of USA](https://www.census.gov/geo/maps-data/data/cbf/cbf_state.html), [Polygon of Wyoming and its Counties](http://explorer.geospatialhub.org/geoportal/catalog/search/resource/details.page?uuid=%7B92A25871-C08A-48CF-8EF1-02870081D0C2%7D), [Polygon of Yellowstone](https://www.sciencebase.gov/catalog/item/4ffb3aebe4b0c15d5ce9fc0b), and [USGS Site for Monthly Data from Specific Site Numbers](https://waterdata.usgs.gov/nwis/monthly?referred_module=sw&search_criteria=site_no_file_attachment&submitted_form=introduction)
