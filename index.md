# Hello world!

I have created this meme to portray my raw feelings towards the course Computer Science 225.
I haved adapted the original four frame meme format to easily display my creation.

R code:
library(magick)
happy_image <- image_read("https://i.imgur.com/XiActUT.jpeg") %>%
  image_scale(300) %>%
  image_crop("300x300+24") %>%
  image_scale(300)
abc <- image_read("https://i.imgur.com/ei8vPNQ.jpeg") %>%
  image_scale(300) %>%
  image_crop("300x300+20") %>%
  image_scale(300) %>%
  image_annotate(text = "The world:", color = "white", size = 30)
cs225 <- image_read("https://i.imgur.com/gHE7ygj.jpeg") %>%
  image_scale(300) %>%
  image_crop("300x300+33") %>%
  image_scale(300) %>%
  image_annotate(text = "CS225:", color = "white", size = 30)
confused_image <- image_read("https://i.imgur.com/gDFqJEw.jpeg") %>%
  image_scale(300) %>%
  image_crop("300x300+24") %>%
  image_scale(300)
title <- image_blank(width = 600, height = 50, color = "#ffffff") %>%
  image_annotate(text = "my mid meme", gravity = "center")

top <- c(abc, happy_image)
tops <- image_append(top)
bottom <- c(cs225, confused_image)
bottoms <- image_append(bottom)
whole <- c(title, tops, bottoms)
meme <- image_append(whole, stack = T)

image_write(meme, "my_meme.png")
