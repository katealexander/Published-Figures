# Boxplots with dots
## Data format
I organized my data into two columns in a tab-delimited .txt document (see "Bax.txt"), with the first column being the distances to the speckle, and the second column being a descriptor of the sample name. To avoid having to organize the order, I number my samples according to the order I would like them in my graph. In R, I will later specify the data to be split into different boxplots depending on the second column.
```
0.01064322	1-dmso
0.01152793	1-dmso
0.01238786	1-dmso
0.135868647	2-2h
0.140944471	2-2h
0.141100735	2-2h
0.011685558	3-6h
0.012268166	3-6h
0.013138652	3-6h
0.270596052	4-9h
0.275619309	4-9h
0.280211396	4-9h
```
## Plot the data
#### Install and load ggplot2
If you do not have the ggplot2 package yet, install the package.
```
install.packages("ggplot2")
```
Then load the library.
```
library(ggplot2)
```
#### Load the data
```
J <- read.table("Bax.txt")
```
#### Check the data format
```
head(J)
          V1     V2
1 0.02802641 1-dmso
2 0.02814364 1-dmso
3 0.02981129 1-dmso
4 0.03212175 1-dmso
5 0.03495171 1-dmso
6 0.03528290 1-dmso
```
#### Using ggplot
```
ggplot(J, aes(x=V2, y=V1, fill=factor(V2))) + geom_boxplot(col="black", size=1, outlier.size = 0) + geom_jitter(color="grey20", size=0.05, alpha= .8) + theme_classic() + ylim(0,2) + scale_fill_brewer(palette = "Oranges")
```
"J" is the table of Bax speckle distance datas containing the distances in V1 and the sample name in V2, "aes" is where you tell ggplot what x and y values to use. In our case the x values are the samples (we'll have a boxplot for each sample), and the y values are the distances to the speckle. Then, we "fill" with different colors depending on the samples (V2).
  
After specifying where the data is coming from, we tell ggplot how to graph it. In this case, we want a boxplot, "geom_boxplot" with a black outline. Then we also want to add all our datapoints using "geom_jitter" to make grey points that are slightly transparent so we can see if spots are on top of one another. geom_jitter, as it sounds, spreads out the points so they are well spread out over the boxplot. 
  
We use ylim to set the y-axis. This makes it so we can reduce the amount of white space in the graph and be able to visualize the differences.
  
Finally, we add what colors we want, using "scale_fill_brewer", in which you can use any number of color palettes. In my paper, I used "Oranges", "Greys", "BuPu" and "Greens". I also replaced with scale_fill_manual(values=c("grey", "#ED553B", "#F2AA3E", "#F2BF44") for more customized colors.





