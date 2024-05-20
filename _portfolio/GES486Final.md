---
title: "GES486 - Ash Tree Succession"
excerpt: "This project is an innovation of my previously done GES386 final project. Key improvements include smoother workflow through RStudio, cartographical production in QGIS, and analysis of clustering in GeoDA<br/><img src='/images/Ash.Succ.png'>"
---

## Introduction

At the beginning of the 21st century, the introduction of the Emerald Ash Borer occurred. This insect originates from the continent of Asia and as the name suggests specializes in boring into Ash trees. Following introduction by being carried over within infected wood, it arrived in a region with no natural predators allowing for rapid expansion in population and geographical range. This expansion has been followed by massive waves of death in Ash trees as the bores interrupted the tree's ability to move nutrients throughout its body.

To study the changes in long-term forest composition a network of scientists with the help of the Smithsonian, helped to create the Forest Global Earth Observatory Network - also known as ForestGEO. This network comprises 78 sites spanning 29 countries with data collected on over seven million trees and 12,000 species. One of these sites is located within the land managed by the University of Maryland, Baltimore County. The ForestGEO site at this location involves the establishment of two 250-meter square plots totaling 12.5 hectares. Plots are named the Knoll which lies within the circular roadway to navigate the campus and the Herbert Run which lies just outside this roadway. These plots were established throughout 2012 and 2013 and designated as permanent research forest plots to ensure no development occurred. Plots are inventoried every 5 years recording all stems above one centimeter in DBH in which other basic tree characteristic information is collected.

I was responsible for a large portion of the data collection during the most recent 2022/2023 inventory. From my experience, I noticed a very worrying trend among the Ash trees, as an extremely large portion of Ash trees were dead. During the academic year of 2022/2023, I attempted to analyze the beginnings of changes within forest compositional trends resulting from the invasion of Emerald Ash Borer. Unfortunately, I ran into many challenges resulting from my lack of GIS experience and no knowledge of any coding languages. Therefore, my goal following gaining stronger GIS and coding knowledge was to improve upon my workflow and develop a reproducible methodology to continue my previous work.

## Methodology

Data used for this project is sourced from Dr. Mathew Baker who is the principal scientist for the ForestGEO plots at UMBC. The data includes all three inventories from 2012/13, 2017/18, and 2022/23 from both the Herbert Run and Knoll sections. Unlike when the data was used during my initial attempt at this analysis, this data has been preprocessed to convert the field measurements to usable UTM coordinates. Within RStudio I primarily used the packages dplyr and sf to help aid in processing data to fit the analysis I aimed to conduct.

Beginning with my data preprocessing, I merged the inventories and set field notations to be set to values usable for analysis. For example, immeasurable trees (either fallen over or missing) were denoted with -99 but when creating buffers later on I wanted to ensure nothing was created and therefore set all -99 values to 0. Once these values were set I condensed my dataset by dropping the preprocessing fields which were no longer needed. This condensation was carried out no only for easier tabular visuals, but also to aid in performance as there have been approximately 9000 unique trees with a total of 57 fields.

With this condensation, I was then able to smoothly transition into calculating measures and new fields. Firstly, I created two new fields named Spec_MostRecent and Spec_First to create accurate tree species identifications. Spec_MostRecent was the field used for further analysis as it took the most recently updated species information and proved to be the most accurate. In addition, critical root zones were calculated by multiplying the DBH by 18 resulting in the radius from the center of the tree being calculated. This then was converted to meters to work best with the st_buffer tool used to visually represent this area. Finally, DBH change was calculated y simply subtracting the third recorded DBH from the first.

Following all of these calculations, the data was exported in a .geojson format. I then loaded this file into QGIS to create hexagonal zones of 10 meters across the extent of the research plots. This file was then used in GeoDa to measure the spatial correlation between the DBH change and species richness using a bivariate model. From the use of tools within GeoDa, results were then brought back into QGIS to create visualizations of the trends found.

## Results

Beginning with the successional model, results showed very large numbers of Ash trees dying at 428 trees disappearing - or 54.6%. As a result, there were large former critical root zones. 94 trees were identified as being new trees following the death of the Ash trees and within the critical root zone measured from the last available DBH. Analysis of these trees revealed many of the succeeding trees were in fact native trees. The top three species of succeeding Ash trees were Bitternut Hickory (24.4%), Black Cherry (15.9%), and Sugar Maple (12.7%). So one can see that these three species are dominating over half of the Ash tree succession. Going further: with the addition of the next two most dominant species of Princess tree (11.7%) and Eastern Redbud (9.5%), 75% of succession is carried out through five species. While most of these species are native - a trend true throughout all of the succeeding species - the fourth most dominant Princess tree is a non-native species. The Princess tree is of a unique concern to local biodiversity as it is a rapidly growing tree with a large leaf area which can quickly crowd out other species from growing. In addition to ecological concerns, their rapidly growing roots posed threats to infrastructure such as roads and pipes.

![Figure One: Succession Layout](images/Ash.Succ.png)

Additionally to show the zonal changes in DBH in centimeters is the layout below.

![Figure Two: Succession Layout](images/DBH.change.png)

Analysis conducted in GeoDa between zonal mean DBH change and species richness also showed trends of interest within the forest plots. In the layout posted below, bivariate clustering analysis is displayed. Importantly one can see that the majority of the clusters identified are high-high indicating large changes in mean DBH change and species richness. Regions where this is seen the most, are typically edges or areas with high disturbance, an expected result as many trees are dying or growing in the same area with many different secondary successional species trying to take advantage of the created gaps. Importantly to note about the confidence of this model was the Morans I was low at -0.015, meaning the correlation observed is weak.

![Figure Three: Clustering Layout](images/Clustering.png)

## Conclusion

Analysis of both the Knoll and Herbert Run ForestGEO research plots revealed incredibly large numbers of Ash trees disappearing and therefore large critical root zones which have been diminished. Spatial correlation revealed that the highly disturbed areas that are the edges - are experiencing high levels of zonal change in DBH and species richness. This statistical result paired with the waves of death among Ash trees leads one to view the beginning trends in succession, as what the future forest composition may appear to be if continuing along this current trend.

## Further Research

As this work was conducted to try and monitor and measure the succession of Ash trees, the biggest challenge faced was the time series of available data. Succession of trees is a relatively slow process as trees grow at different rates due to a variety of factors. To be able to successfully conclude the succession taking place following the death of Ash trees, increased data would be required. Further development of this project would continue to use the methods developed in this workflow and apply them to the following inventories. 

Going into this project I was aware of the challenges the data would face in being able to draw strong conclusions. In being cognizant of this, I prioritized not only the creation of reproducible research methods but also made a strong effort to explain the methods being used throughout the workflow.

