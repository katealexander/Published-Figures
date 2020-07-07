# Transcription site intensity versus distance to speckle


```
library(ggplot2)
```
```
A <- read.table("distsAndIntensities_SONkd.txt")
```

```
head(A)
         V1       V2     V3
1 0.4242252 2.702391 1-dmso
2 0.3817663 2.641013 1-dmso
3 1.7040366 2.623444 1-dmso
4 0.9086680 2.302462 1-dmso
5 0.2965198 2.175460 1-dmso
6 0.2215420 1.993592 1-dmso
```

```
ggplot(A[A$V3 == "1-dmso",], aes(V1, V2)) + stat_density_2d(aes(fill = ..density..), geom = 'raster', contour = FALSE) + scale_fill_viridis_c(option="B", direction = 1) + coord_cartesian(expand = FALSE) + geom_point(shape = 1, col = 'white') + xlim(0,1.5) + ylim(0,15)
```

```
 ggplot(A[A$V3 == "2-2h",], aes(V1, V2)) + stat_density_2d(aes(fill = ..density..), geom = 'raster', contour = FALSE) + scale_fill_viridis_c(option="B", direction = 1) + coord_cartesian(expand = FALSE) + geom_point(shape = 1, col = 'white') + xlim(0,1.5) + ylim(0,15)
 ```
 
