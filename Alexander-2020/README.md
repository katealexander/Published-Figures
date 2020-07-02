# p53 transcription factor mediates nuclear speckle association of target genes
This repository contains instructions for making figures in R for the figures found within "p53 transcription factor mediates nuclear speckle association of target genes". These data include tons of RNA- and DNA-FISH image analysis data, and [SON TSA-seq](https://github.com/katealexander/TSAseq-Alexander2020).

## Boxplot with dots
The boxplot shows the quartiles of the data, while the dots allow visuallization of the data distribution. Boxplots with dots for each of the data points was my favorite way to represent much of my RNA- and DNA-FISH data: distance to speckle, number of molecules per cell, and intensity of transcription sites.
## Transcription site intensity versus distance to speckle
Visualizing the relationship between the distance of a transcription site to nuclear speckles and the intensity of that transcription site was complicated at first because so many of the datapoints were atop one another. I found scatterplots with density heatmaps underneath to be a good solution to visualize the density of the data.
