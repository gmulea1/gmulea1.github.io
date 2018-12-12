---
title: Final Project Proposal
feature_image: ""
feature_text: |
  <font size="7" color='black'><span style="background-color: #FDFDFD"> </span></font><br>
  <font size="4" color='black'><span style="background-color: #FDFDFD"> </span></font>
  
---

~~Continuing from my project two, I am going to look at the chamge in zomomg and how it relates (if at all) to the spatial distribution of different races.  I plan on using the same data from Project two im addition to census demographic data.  [Vital Signs Archive](https://bniajfi.org/vital_signs/archives/).  First, I am going to use just the Residential Data from Porject 2, and seperate it into its different types fo Residential Data.  Next, I plan to use a SQL statement to spatial join different year demographics data.  Than, I will use python to run analysis on the demographics data and land use change data to figure out the amount of change in each census tract.  I will compare this to the dominant race in that tract. I can use GeoDa to run a cluster analysis on the amount of chamge for each tract and use significance filters to determine if the data shows anything of importance.~~

~~I choose this, because it ties in with my project 2 and expands on it.  This will be more involved than the labs, because it involves multiple tools and programs to complete.  Unlike the GeoDa lab I will be uskng my own data that I created and not a directly downloaded data set.  I also will create another gif using photoshop to visualize the changes.~~


For this project, I will be analyzing annual water flows for rivers and streams in the Yellowstone National Park Area.  I want to figure out if catchment area size affects the rate of snowmelt discharge through streams in the Yellowstone Area.  To do this I will first use SQL to select USGS Stream Gages that within a 10 mile buffer zone of Yellowstone.  Next I will download data from USGS's website and use python to find the max and min disharge values for specific streams and match that to the Gages around Yellowstone.  Using Python, I will create a script to match the max and min values to their respective Gages and update the attribute table.  

My data will come from [DEM of Yellowstone Area](https://viewer.nationalmap.gov/basic/?category=ned#productGroupSearch), [Stream Polyon](http://download.geofabrik.de/north-america.html), [Polygon of USA](https://www.census.gov/geo/maps-data/data/cbf/cbf_state.html), [Polygon of Wyoming and its Counties](http://explorer.geospatialhub.org/geoportal/catalog/search/resource/details.page?uuid=%7B92A25871-C08A-48CF-8EF1-02870081D0C2%7D), [Polygon of Yellowstone](https://www.sciencebase.gov/catalog/item/4ffb3aebe4b0c15d5ce9fc0b), and [USGS Site for Monthly Data from Specific Site Numbers](https://waterdata.usgs.gov/nwis/monthly?referred_module=sw&search_criteria=site_no_file_attachment&submitted_form=introduction)
