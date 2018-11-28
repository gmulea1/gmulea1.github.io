## Lab 6
Gregory Mulea

### Part 1
**Screenshots:**

Cluster Map 999 Permutations
![999 Perms](999_perm.PNG)

Cluster Map 99999 Permutations
![99999 Perms](99999_perm.PNG)

Low - High
![Low-High](low-high.PNG)

Bonferroni Map
![Bonferroni](bonferroni.PNG)

False Discovery Rate Map
![FDR](FDR.PNG)

Cores and Neighbors
![Cores and Neighbors](cores_neighbors.PNG)

Conditional Map
![Conditional](local.PNG)

Local Guerry Map
![Guerry](guerry_local.PNG)

Local Guerry Map with Negative Highlighted
![Guerry Negative](guerry_negative.PNG)

Guerry Map with 99999 Permutations and a Significance of 0.01
![99999 Perms and p - 0.01](guerry_99999_p0.01.PNG)

Getis-Ord Map 999 Permutations
![Gi 999](Gi_999.PNG)

Getis-Ord Map 99999 Permutations and Significance from FDR
![Gi 999](Gi_99999_FDR.PNG)

### Part 2/3
First I used QGIS to link the bottom section to its neighbors to properly create a full analysis.  I decided to look at the difference between households with a median income of either greater than $75,000 or under $25,000.  In order to do this I divided the percentage values by 100 and multiplied it by the total population.  Than I ran a basic cluster analysis on both of those to create cluster maps.

`Under $25,000 (Top) versus Over $75,000 (Bottom)`
![Cluster Maps](income.PNG)

This shows that in areas that have a lot of households under $25,000 are located mostly in the North West area of the middle of Baltimore City in a large cluster.  Areas with a lot of households above $75,000 are more scattered around the edges of the city.

I am overall proud of what I did because I was able to edit the shapefile to ensure the bottom section is included in the analysis and also editing the table through GeoDa to give me useful numbers to run an analysis.
