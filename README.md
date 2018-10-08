# Zoning in Baltimore City

In this project, I am analyzing the distribution of zones versus the distance from the Patapsco River.

In order to achieve this analysis I used the real_property dataset from the Baltimore City Open Data Source.

First I had to sort and reclassify the zoning column to fit the categories of Commercial, Residential, Industrial, Open Space, Office, Education, Transit, Historic, and Other.  I used a case - when function within the field calculator.

<details>
<summary>
<i>case - when </i>
</summary>
<p>
> case
when "zonecode" = 'C-1' then 'Commercial'
when "zonecode" = 'C-1VC' then 'Commercial'
when "zonecode" = 'C-2' then 'Commercial'
when "zonecode" = 'C-4' then 'Commercial'
when "zonecode" = 'C-5IH' then 'Commercial'
when "zonecode" = 'C-5HT' then 'Commercial'
when "zonecode" = 'C-5TO' then 'Commercial'
when "zonecode" = 'C-5HS' then 'Commercial'
when "zonecode" = 'C-5DC' then 'Commercial'
when "zonecode" = 'C-3' then 'Commercial'
when "zonecode" = 'C-2*' then 'Commercial'
when "zonecode" = 'C-1E*' then 'Commercial'
when "zonecode" = 'C-5DC*' then 'Commercial'
when "zonecode" = 'C5TO*' then 'Commercial'
when "zonecode" = 'C-5-G' then 'Commercial'
when "zonecode" = 'C-1-E' then 'Commercial'
when "zonecode" = 'C-5DE' then 'Commercial'
when "zonecode" = 'BSC' then 'Education'
when "zonecode" = 'EC-2' then 'Education'
when "zonecode" = 'EC-1' then 'Education'
when "zonecode" = 'H' then 'Historic'
when "zonecode" = 'I-MU' then 'Industrial'
when "zonecode" = 'I-1' then 'Industrial'
when "zonecode" = 'I-2' then 'Industrial'
when "zonecode" = 'MI' then 'Industrial'
when "zonecode" = 'OR-2*' then 'Office'
when "zonecode" = 'OR-1' then 'Office'
when "zonecode" = 'OR-1*' then 'Office'
when "zonecode" = 'OR-2' then 'Office'
when "zonecode" = 'OIC' then 'Office'
when "zonecode" = 'OS' then 'Open Space'
when "zonecode" = 'OS*' then 'Open Space'
when "zonecode" = 'R-5*' then 'Residential'
when "zonecode" = 'R-1-C' then 'Residential'
when "zonecode" = 'R-1-A' then 'Residential'
when "zonecode" = 'R-6*' then 'Residential'
when "zonecode" = 'R-1-B' then 'Residential'
when "zonecode" = 'R-1' then 'Residential'
when "zonecode" = 'R-3*' then 'Residential'
when "zonecode" = 'R-1-E' then 'Residential'
when "zonecode" = 'R-1E*' then 'Residential'
when "zonecode" = 'R-1-D' then 'Residential'
when "zonecode" = 'R-2' then 'Residential'
when "zonecode" = 'R-4*' then 'Residential'
when "zonecode" = 'R-1*' then 'Residential'
when "zonecode" = 'R-9' then 'Residential'
when "zonecode" = 'R-7' then 'Residential'
when "zonecode" = 'R-8' then 'Residential'
when "zonecode" = 'R-6' then 'Residential'
when "zonecode" = 'R-8*' then 'Residential'
when "zonecode" = 'R-10' then 'Residential'
when "zonecode" = 'R-7*' then 'Residential'
when "zonecode" = 'R-3' then 'Residential'
when "zonecode" = 'R-5' then 'Residential'
when "zonecode" = 'R-4' then 'Residential'
when "zonecode" = 'TOD-3' then 'Transit'
when "zonecode" = 'TOD-4' then 'Transit'
when "zonecode" = 'TOD-1' then 'Transit'
when "zonecode" = 'TOD-2' then 'Transit'
when "zonecode" = 'TOD4*' then 'Transit'
else 'Other'
end
</p>
</details>

![Image]( gmulea1.github.io/balt_zones.png )

![Image]( gmulea1.github.io/hex1.JPG "3D Veiw of Baltimore City")
[3D Image Download](gmulea1.github.io/hex.gltf)
