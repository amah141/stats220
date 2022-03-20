# **Hello everyone! This is my unique original meme I made using RStudio!**
## I created this meme to reflect something we all have gone through as students - sleep deprivation and how even at work or while studying sometimes we feel like we want to sleep. 

### *The Meme is original and new as its something that has never been created before. I had to manually extract the frames from this GIF image shown below and then pick the appropriate images to use.*

![](my_meme.png)

## R Code Below!

```r
library(magick)

image1 <- image_read("https://preview.redd.it/yu38pkegr9i51.png?auto=webp&s=c27a41570c82598bb521596283226f9f61cf164b") %>%
  image_scale(500)

image2 <- image_read("https://www.cnnphilippines.com/.imaging/mte/demo-cnn-new/750x450/dam/cnn/2015/9/26/Homer_Simpson_CNNPH.png/jcr:content/Homer_Simpson_CNNPH.png") %>%
  image_scale(500)

image3 <- image_read("https://i.ytimg.com/vi/JeQzivuFouM/hqdefault.jpg") %>%
  image_scale(500)

image1_text <- image_blank(width = 500, 
                           height = 465, 
                           color = "#000000") %>%
  image_annotate(text = "Normal \nSleeping",
                 color = "#FFFFFF",
                 size = 65,
                 font = "Impact",
                 gravity = "center")

image2_text <- image_blank(width = 500, 
                           height = 300, 
                           color = "#000000") %>%
  image_annotate(text = "Medium \n Sleep while Working",
                 color = "#FFFFFF",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

image3_text <- image_blank(width = 500, 
                           height = 380, 
                           color = "#000000") %>%
  image_annotate(text = "Hard\n Sleep while Studying",
                 color = "#FFFFFF",
                 size = 55,
                 font = "Impact",
                 gravity = "center")

row1 <- c(image1, image1_text) %>%
  image_append()

row2 <- c(image2, image2_text) %>%
  image_append()

row3 <- c(image3, image3_text) %>%
  image_append()

final<-c(row1, row2, row3) %>%
  image_append(stack = TRUE)

final

image_write(final, "mymeme.png")

```













