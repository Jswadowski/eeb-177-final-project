---
title: "week-8-hw"
author: "Jeremy Wadowski"
date: "March 8, 2017"
output: md_document
---
```{r}
library(ggplot2)
canids <- read.csv("/home/eeb177-student/Desktop/eeb-177/homework_bk/canid-ranges-sorted.csv", header = F, as.is = T)
names(canids) <- c("genus", "species", "minage", "maxage")
head(canids)

canid_occ <- ggplot(canids, aes( species, ymin = maxage, ymax=minage, colour = genus))
canid_occ <- canid_occ + geom_linerange()
canid_occ

canid_occ <- canid_occ + theme(legend.position="none")
canid_occ

canid_occ <- canid_occ + coord_flip()
canid_occ

canid_occ <- canid_occ +  theme(axis.text.y = element_text(size=3))
canid_occ

canid_occ <- canid_occ + theme(axis.ticks.y=element_blank())

canid_occ <- canid_occ + scale_y_continuous(limits=c(0, 40), expand = c(0, 0), breaks=c(0, 10, 20, 30, 40))

canid_occ <- canid_occ + labs(title = "Canid Fossil Occurrences", x = "Species", y = "Ma ago") + theme(plot.title = element_text(hjust = 0.5, size=22, face = "bold"), axis.title =element_text(size=20))
canid_occ

ggsave(filename = "canid-occ.pdf", plot = canid_occ)
```
# Part 7 Questions
- What taxonomic group is displayed? 
--> Displayed are canids. 
- How many unique fossil species are contained within it?  There are 211 unique species.
- How many unique fossil genera?  There are 206 unique genera.
- What species has the longest fossil range?  Cynodictis has the longest fossil range.


# Dino Fossil Record
```{r}
library("ggplot2")
Dino <- read.csv("/home/eeb177-student/Desktop/eeb-177/homework_bk/canid-ranges-sorted.csv", header = F, as.is = T)
names(Dino) <- c("genus", "species", "minage", "maxage")
head(Dino)

Dino_occ <- ggplot(Dino, aes( species, ymin = maxage, ymax=minage, colour = genus))
Dino_occ <- canid_occ + geom_linerange() 
Dino_occ <- canid_occ + theme(legend.position="none") 
Dino_occ <- canid_occ + coord_flip() 
Dino_occ <- canid_occ +  theme(axis.text.y = element_text(size=3)) 
Dino_occ <- canid_occ + theme(axis.ticks.y=element_blank()) 
Dino_occ <- canid_occ + scale_y_continuous(limits=c(0, 40), expand = c(0, 0), breaks=c(0, 10, 20, 30, 40))
Dino_occ <- canid_occ + labs(title = "Dino Fossil Occurrences", x = "Species", y = "Ma ago") + theme(plot.title = element_text(hjust = 0.5, size=22, face = "bold"), axis.title =element_text(size=20)) 
Dino_occ
ggsave(filename = "Dino-occ.pdf", plot = Dino_occ) 

```
# Part 2

## Exploring Data Frames
```{r}
#Challenge 1
df <- data.frame(first = c('Jeremy'), last = c('Wadowski'), lucky_number = c(8), stringsAsFactors = FALSE)
df <- rbind(df, list('Adi', 'Brett', 238) )
df <- cbind(df, coffeetime = c(TRUE,TRUE))

#Challenge 2
download.file("https://raw.githubusercontent.com/swcarpentry/r-novice-gapminder/gh-pages/_episodes_rmd/data/gapminder-FiveYearData.csv", destfile = "data/gapminder-FiveYearData.csv")
gapminder <- read.csv(file = "data/gapminder-FiveYearData.csv")
#cannot download all files??

#Challenge 3
#Can't complete because the files from challenge 2 cannot be downloaded.

```
# Subsetting Data
```{r}


```
