[![License: MIT](https://img.shields.io/github/license/jhelvy/splitKbCompare)](https://github.com/jhelvy/splitKbCompare/blob/master/LICENSE.txt)

<a href="https://github.com/jhelvy/splitKbCompare" target="_blank">
<i class="fa fa-github fa-lg"></i></a> Copyright (c) 2020 John Helveston

### Overview

This app is an interactive tool for comparing layouts of different split mechanical keyboards built for the community of [ergonomic keyboard](https://www.reddit.com/r/ErgoMechKeyboards/) users. Split keyboards offer an ergonomic solution to many issues that make regular keyboards painful or uncomfortable to use, but finding which keyboard is right for you can be costly and difficult. Most split keyboards come as DIY kits, making it difficult (if not impossible) to compare different keyboard layouts prior to building them. This app offers one solution to this problem.

More comprehensive lists of ergonomic keyboards are available here:

- [mechdb.net](https://mechdb.net/keyboards)
- [awesome-split-keyboards](https://github.com/diimdeep/awesome-split-keyboards)

### Features

Click one of the "print" buttons to download a printable PDF of the true-to-scale keyboard layouts (8.5" x 11" or A4 sizes).

Filter the keyboard list:

- Maximum number of keys.
- Has a number row at the top.
- Degree of stagger across the key columns.
- Supports rotary encoders.
- Wireless.
- One-piece board or two halves.
- Availability: DIY and/or pre-built.

### Run locally

The app is hosted for [free online](https://jhelvy.shinyapps.io/splitkbcompare/), but you can also run the app locally on your computer by following these steps:

1. Install [R](https://cloud.r-project.org/)
2. Run this code in an R terminal (run 'R', e.g. '/usr/bin/R' or 'Rgui.exe') to install the necessary package dependencies:

```
install.packages(c(
    "shiny", "DT", "dplyr", "shinythemes", "shinyWidgets", "magick", "readr",
    "RColorBrewer", "markdown", "rmarkdown"
))
```

3. Run this in R to launch the app:

```
shiny::runGitHub('jhelvy/splitKbCompare')
```

### Under the hood

This app was built using the [R shiny package](https://shiny.rstudio.com/). Shiny apps are typically used to display data and create interactive dashboards. This app has a different purpose: to help the community of ergonomic keyboard users and hobbyists compare different keyboards.

The app uses the [magick library](https://cran.r-project.org/web/packages/magick/vignettes/intro.html) to overlay images of different keyboard layouts of the user's choosing. The app dynamically changes the colors of each keyboard image in real time to help identify the contours of each different keyboard. To print the image to scale, the overlay image is inserted into a RMarkdown document and converted into a true-to-scale PDF. The app is hosted for free on [shinyapps.io](https://www.shinyapps.io/), and the [open source code is hosted on Github](https://github.com/jhelvy/splitKbCompare).

### Contributing

If you would like to contribute to this package, feel free to fork this repo and send a PR. You can also [file an issue](https://github.com/jhelvy/splitKbCompare/issues) and I'll try and get to it when I have time.

### Added new keyboards

I am no longer going to keep adding new keyboards to this app. It is a manual process and time-consuming, and I just don't have the time to maintain it. Apologies to the keyboard developers out there. If you want to add a keyboard yourself, the process I have used is to hand-edit the `images/overlays.ai` file to add the switch plate svg and label, and then re-export all the layers as png files (one for each keyboard). If you have access to Adobe Illustrator and want to do that process, send me a PR and I'll add it.
