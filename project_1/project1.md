---
title: Project 1
feature_image: "p1_banner.PNG"
feature_text: |
  <font size="7" color='black'><span style="background-color: #F9F9F9"> Zoning in Baltimore </span></font><br>
  <font size="4" color='black'><span style="background-color: #F9F9F9"> With Respect to Distance from the Patapsco River </span></font>
  
---

In this project, I am analyzing the distribution of zones versus the distance from the Patapsco River.

In order to achieve this analysis I used the real_property dataset from the Baltimore City Open Data Source.

First I had to sort and reclassify the zoning column to fit the categories of Commercial, Residential, Industrial, Open Space, Office, Education, Transit, Historic, and Other.  I used a case - when function within the field calculator.

<details>
<summary>
<i>Click to View case - when </i>
</summary>
<p>
<blockquote> case <br />
when "zonecode" = 'C-1' then 'Commercial'<br />
when "zonecode" = 'C-1VC' then 'Commercial'<br />
when "zonecode" = 'C-2' then 'Commercial'<br />
when "zonecode" = 'C-4' then 'Commercial'<br />
when "zonecode" = 'C-5IH' then 'Commercial'<br />
when "zonecode" = 'C-5HT' then 'Commercial'<br />
when "zonecode" = 'C-5TO' then 'Commercial'<br />
when "zonecode" = 'C-5HS' then 'Commercial'<br />
when "zonecode" = 'C-5DC' then 'Commercial'<br />
when "zonecode" = 'C-3' then 'Commercial'<br />
when "zonecode" = 'C-2*' then 'Commercial'<br />
when "zonecode" = 'C-1E*' then 'Commercial'<br />
when "zonecode" = 'C-5DC*' then 'Commercial'<br />
when "zonecode" = 'C5TO*' then 'Commercial'<br />
when "zonecode" = 'C-5-G' then 'Commercial'<br />
when "zonecode" = 'C-1-E' then 'Commercial'<br />
when "zonecode" = 'C-5DE' then 'Commercial'<br />
when "zonecode" = 'BSC' then 'Education'<br />
when "zonecode" = 'EC-2' then 'Education'<br />
when "zonecode" = 'EC-1' then 'Education'<br />
when "zonecode" = 'H' then 'Historic'<br />
when "zonecode" = 'I-MU' then 'Industrial'<br />
when "zonecode" = 'I-1' then 'Industrial'<br />
when "zonecode" = 'I-2' then 'Industrial'<br />
when "zonecode" = 'MI' then 'Industrial'<br />
when "zonecode" = 'OR-2*' then 'Office'<br />
when "zonecode" = 'OR-1' then 'Office'<br />
when "zonecode" = 'OR-1*' then 'Office'<br />
when "zonecode" = 'OR-2' then 'Office'<br />
when "zonecode" = 'OIC' then 'Office'<br />
when "zonecode" = 'OS' then 'Open Space'<br />
when "zonecode" = 'OS*' then 'Open Space'<br />
when "zonecode" = 'R-5*' then 'Residential'<br />
when "zonecode" = 'R-1-C' then 'Residential'<br />
when "zonecode" = 'R-1-A' then 'Residential'<br />
when "zonecode" = 'R-6*' then 'Residential'<br />
when "zonecode" = 'R-1-B' then 'Residential'<br />
when "zonecode" = 'R-1' then 'Residential'<br />
when "zonecode" = 'R-3*' then 'Residential'<br />
when "zonecode" = 'R-1-E' then 'Residential'<br />
when "zonecode" = 'R-1E*' then 'Residential'<br />
when "zonecode" = 'R-1-D' then 'Residential'<br />
when "zonecode" = 'R-2' then 'Residential'<br />
when "zonecode" = 'R-4*' then 'Residential'<br />
when "zonecode" = 'R-1*' then 'Residential'<br />
when "zonecode" = 'R-9' then 'Residential'<br />
when "zonecode" = 'R-7' then 'Residential'<br />
when "zonecode" = 'R-8' then 'Residential'<br />
when "zonecode" = 'R-6' then 'Residential'<br />
when "zonecode" = 'R-8*' then 'Residential'<br />
when "zonecode" = 'R-10' then 'Residential'<br />
when "zonecode" = 'R-7*' then 'Residential'<br />
when "zonecode" = 'R-3' then 'Residential'<br />
when "zonecode" = 'R-5' then 'Residential'<br />
when "zonecode" = 'R-4' then 'Residential'<br />
when "zonecode" = 'TOD-3' then 'Transit'<br />
when "zonecode" = 'TOD-4' then 'Transit'<br />
when "zonecode" = 'TOD-1' then 'Transit'<br />
when "zonecode" = 'TOD-2' then 'Transit'<br />
when "zonecode" = 'TOD4*' then 'Transit'<br />
else 'Other'<br />
end
</blockquote>
</p>
</details>

---
Next, I used a SQLite Database to create buffers at each mile away from the Patapsco River.

> ##### Example for the buffer from 5 - 6 miles from the River

> select st_difference(st_buffer(st_transform(geometry, 26913), 1610\*6), st_buffer(st_transform(geometry, 26913), 1610\*5)) from water

I calculated the geometry for each property zone and calculated the total area for each buffer area.  Than, using the SQLite Database again I calculated the area of each zoning type and the percent of each zone in the each buffer.

> ##### Example for the buffer 1 mile or less from the River

> select simple, sum(area) as "1 Mile Area", (sum(area)/totalarea)*100 as "1 Mile Percent" from "1mile_zone" group by simple order by "1 Mile Percent" desc

Using the percent from each buffer zone, I created a graph in excel that compares the distance to the percent area for each zone type.  I generated a pdf combining the graph and a map of the Baltimore City Zones (NAD 83 / Maryland Projection).

![Image](balt_zones.png)

This graph reveals the relationship of certain zones compared to distance from the River.  There are 4 main zones that change with distance: <span style="color:#2f57e7">Commercial</span>, <span style="color:#37a040">Residential</span>, <span style="color:#eada46">Industrial</span>, and <span style="color:#00ec00">Open Space</span>.  The rest of the zone types remain below 10% at any distance from the River.

The Commercial and Industrial Zones dominate the first mile from the River with a moderate amount of Residential and low Open Space.  While Commercial and Industrial occupy the same percent of area they do not occupy the same Geographical areas.  Commercial Zones occupies the area near to the North of the River (the center of Baltimore City) while the Industrial Zones occupy the majority of the area South of the city along the River.

As distance increases from the River; Commercial and Industrial Zoning decreases and Residential Zoning increases rapidly.  Open Space increases and has a small peak at 3 miles and then decreases over the rest of distance.  Residential Zones Dominate the area after 3/4 miles away from the River, and reach almost 90% of the total zoning area.

---

Lastly, I created a grid of hexagons to be used for 3D Viewing.  I used a spatial zone to join the grid to the percent of each zone.  Using Qgis2threejs plugin in QGIS I created a 3D image of the relative percent colored by the type of zoning. This best shows the sharp increase in the Residential Zoning as you move further from the River.

![Image](hex1.JPG "3D View of Baltimore City")
[3D Image Download](hex.gltf)


#### Gregory Mulea
