# 👋 Kia ora 👋
*Welcome to my test website* 🎇

## 👶 Personal Information 👶
I am a student at the [**University of Auckland 👇**](https://www.auckland.ac.nz/en.html) <br />
![](https://upload.wikimedia.org/wikipedia/en/thumb/a/ac/University_of_Auckland_Coat_of_Arms.png/225px-University_of_Auckland_Coat_of_Arms.png) <br />
**👇My Favorite👇** <br />
- [*Basketball*](https://www.nba.com/) 🏀 
- [*Football*](https://www.bundesliga.com/en/bundesliga) ⚽
- *Video Games* ⚔️
- *Coffee* ☕

## 💻 Memes 💻
Below is a meme I made using the R package [**_{magick}_**](https://cran.r-project.org/web/packages/magick/vignettes/intro.html). <br />
🔥[**LBJ**](https://en.wikipedia.org/wiki/LeBron_James) and [**KD**](https://en.wikipedia.org/wiki/Kevin_Durant)🔥
![](my_meme.png) 
These two basketball players are both from NBA, LBJ is currently playing for Los Angles Lakers🔥<br />
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/Los_Angeles_Lakers_logo.svg/360px-Los_Angeles_Lakers_logo.svg.png" width="400" height="300"> <br />
And KD is currently playing for Brooklyn Nets🔥 <br />
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Brooklyn_Nets_newlogo.svg/420px-Brooklyn_Nets_newlogo.svg.png" width="300" height="300">

## 🐳 Summary of my memes 🐳
- My memes is about two of my favorite NBA players.
- I found these pictures on internet, and I combine them together. <br />

**Code**👇
```
"""
Student ID: bxue488
Student Name: Baichen Xue
"""

library(magick)

lbj <- image_read("https://library.sportingnews.com/styles/crop_style_16_9_desktop/s3/2021-12/lebron-james-los-angeles-lakers_kej02uf93prj18vqxkh8dfnqk.png?itok=tDIfJFZJ") %>%
  image_scale(1000)
lbj_text <- image_blank(width = 1000,
                        height = 300,
                        color = "#987094") %>%
  image_annotate(text = "LeBron James",
                 color = "#232323",
                 size = 70,
                 font = "Lato",
                 gravity = "center")

kd <- image_read("https://cdn.vox-cdn.com/thumbor/HR19kpEzfpMWTFNb2tZmDo_BOxU=/0x0:6314x4133/920x613/filters:focal(2263x1562:3273x2572):format(webp)/cdn.vox-cdn.com/uploads/chorus_image/image/70245603/1237082434.0.jpg") %>%
  image_scale(1000)
kd_text <- image_blank(width = 1000,
                       height = 300,
                       color = "#734436") %>%
  image_annotate(text = "Kevin Durant",
                 color = "#353535",
                 size = 70,
                 font = "Lato",
                 gravity = "center")

queenstown <- image_read("https://www.skyline.co.nz/media/3644/skyline-queenstown_winter-wonderland.FgJHqQ.jpg?width=1200") %>%
  image_scale(1000)
qt <- image_composite(image_scale(queenstown, "x1000"), lbj, offset = "+200+100")
queenstown_text <- image_blank(width = 1000,
                        height = 300,
                        color = "#561517") %>%
  image_annotate(text = "LBJ in Queenstown",
                 color = "#181818",
                 size = 70,
                 font = "Lato",
                 gravity = "center")



lbj_vector <- c(lbj, lbj_text)
kd_vector <- c(kd, kd_text)
qt_vector <- c(qt, queenstown_text)
final_vector <- c(lbj_vector, kd_vector, qt_vector)
image_append(final_vector, stack = TRUE)
```
