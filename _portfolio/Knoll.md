---
title: "Ash Tree Succession Model"
excerpt: "Analyzing changes in forest patch composition following the invasion of Emerald Ash Borer <br/><img src='/images/All_trees.png'>"
collection: portfolio
---

For the academic year 2022-2023, I served as an Assistant Project Manager for field data collection at UMBC. This assignment involved the collection of dbh measurements, tree characteristics, and geographic location which are metrics used and recorded by the ForestGEO network. This network aims to monitor and measure long-term changes in forest composition across the globe through the use of forest inventories among research plots. UMBC's involvement in this initiative is through two forest plots - totaling 12.5 hectares - in which over seven thousand stems are present. The designation of these plots, procedure enforcement, data collection, and data processing are managed by UMBC's Geography and Environmental Science department professors Dr. Baker and Dr. Ellis.

As this project was coming to an end, I took it upon myself to analyze any trends observable among the relatively short data that had been collected and in the process of being collected. I did this analysis on one of the research plots named the Knoll, as the second plot's third inventory was still being conducted. Forestry data for both plots had been originally gathered in 2012-2013 through the means of an inventorying crew who established quadrats for the following inventories to guide measurements of the locations of new trees. Inventories have been coordinated to occur every 5 years following, therefore, at the time of the beginning of this project I was using the first inventory previously mentioned, the second inventory in 2017-2018, and the ongoing third inventory in 2022-2023.

Due to the ongoing nature of the third inventory, I was given the task of preprocessing the field data and making it usable within a GIS. The field measurements of the locations of new stems (new tree stems had the requirement of being greater than one centimeter in DBH) were made in meters from a known and trusted location such as quadrat pin locations or trees. These measurements then had to be converted into UTM coordinates that could be used to mark tree locations.

After this preprocessing was completed, I then chose the Fraxinus genus as my focus subject; the recent introduction and invasion of Emerald Ash Borer and its effect on local Ash tree populations was of key interest. Using the large 10-year time series of forest composition within these plots, I then identified and subsetted the Ash trees from the first and second inventory that no longer had a DBH within the third inventory. Unfortunately, this subset of trees was much larger than initially thought. Between the second and third inventory alone, 200 trees were lost, and of the 220 trees remaining in the third inventory 106 of them were labeled as dead. Minimal Ash succession was observed with only a mere 18 new trees being observed. 

From this subset of trees I created a buffer of the tree's basal area, a measure derived from the DBH information available. Then another subset was created of all of the new trees observed within the third inventory. Both the buffer of former Ash tree basal areas and the subset of new tree locations were used to generate a selection, and subset, of the successional trees within the Ash tree basal areas. 

Results found that Bitternut Hickory dominated the succession at 21.6% of the species composition, followed by Black Cherry at 15.5% and Sugar Maple at 13.8% of the successional species composition. Seeing Black Cherry among the three highest successional species was of no surprise as Black Cherry comprises 15.6% of the Knoll forest patch - a percentage very similar to that of the successional species found. On the other hand, both Bitternut Hickory and Sugar Maple were already both dominant species within the Knoll but excelled at succeding in areas of former Ash trees.

The full methodology can be found at the following [ArcGIS Online StoryMap](https://storymaps.arcgis.com/stories/591c609fe65048279708a75e9a180293)








