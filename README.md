# Creating-corporate-colour-palettes-for-ggplot2

The details of the codeset and plots are included in the attached Microsoft Word Document (.docx) file in this repository. 
You need to view the file in "Read Mode" to see the contents properly after downloading the same.

A Brief Introduction
======================

Australia-themed Colour Palettes

Ochre is a brownish-yellow pigment that occurs naturally in soils across Australia. Historically, ochre has been used for artwork by many indigenous cultures, including the Aboriginal people of Australia.The goal of ochRe is to provide colour palettes inspired by Australian art, landscapes and wildlife. The palettes can be used in conjunction with ggplot2 or plot to provide colours to data plots. There are 16 different palettes (at the moment!), each one based on an iconic Australian artwork, landscape or creature. Some palettes are more suitable for displaying qualitative data, others will look fabulous used in sequential plots. More information can be found in the vignette, including which palettes work best for those with impaired colour vision.

# load the ochRe vignette
        vignette("ochre")

Installation
================
You can install ochRe from github with:

# You need to install the 'devtools' package first
        Library("ochRe")

The Palettes
=============

![image](https://user-images.githubusercontent.com/26252963/148026665-84ac2377-43af-42ce-b836-d8440fd1fdf5.png)

        pal_names <- names(ochre_palettes)

        par(mfrow=c(length(ochre_palettes)/2, 2), lheight = 2, mar=rep(1, 4), adj = 0)
        for (i in 1:length(ochre_palettes)){
            viz_palette(ochre_palettes[[i]], pal_names[i])
        }

Example
==========

This is a basic example of how to use the namatjira_qual palette in a plot.

        library(ochRe)
        library(ggplot2)
        ggplot(diamonds) + geom_bar(aes(x = cut, fill = clarity)) +
          scale_fill_ochre()
  
  ![image](https://user-images.githubusercontent.com/26252963/148026761-2ea20eeb-ac5d-48a4-bef4-74a334334085.png)


In this example we use the winmar palette directly via the colorRampPalette() function (for the base plot connoisseurs).

## basic example code
        pal <- colorRampPalette(ochre_palettes[["winmar"]])
        image(volcano, col = pal(20))

Individual palettes can be visualised using the viz_palette function

![image](https://user-images.githubusercontent.com/26252963/148026852-122ea678-fb2f-46fa-a045-7592aeb74e4d.png)


viz_palette(ochre_palettes[["tasmania"]])
![image](https://user-images.githubusercontent.com/26252963/148026913-d6baff13-68a6-4d55-96fe-d478c151c8b9.png)



