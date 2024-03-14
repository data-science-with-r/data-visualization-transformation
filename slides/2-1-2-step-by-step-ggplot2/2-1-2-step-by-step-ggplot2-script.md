Hello, in this video we're going to talk about the specifics and syntax of visualizing data with the ggplot2 package and we're going to do so using data on penguins! 

>>

First, a bit on gglot2 as a package.

>>

>> ggplot2 is tidyverse's data visualization package, so to access it, we load it with library(tidyverse)
>> gg in ggplot2 stands for Grammar of Graphics, inspired by the book Grammar of Graphics by Leland Wilkinson
>> A useful resource for learning about the package and its functions is the package website, at ggplot2.tidyverse.owg
>> And the code always follows the same structure: ggplot, then the data, then aesthetic mappings, then any geoms, and finally any other options


>>

We've seen this plot of mass and height of star wars characters, but here it is again, with the code and any associated warnings this time.

The structure of ggplot2 code looks almost always is the same: 
>> we start with the ggplot function, where the first argument is the data that you want to plot and the second argument defines the aesthetic mappings using the aes function -- in this template we have only defined the x and y aesthetics, for example. This one is somewhat unusual, you're passing a function, aes, as the argument of another function, ggplot. You'll see more of this as we progress through the course, though more often you'll see data frame or variable names being passed to function arguments.
>> and then we add on another layer -- a geom layer -- which defines the geometric shapes with which you want to represent your data 
>> and then optionally, though in many cases are recommendedly, we add further layers to the plot to make our plot a little bit easier to read, a little bit easier to glean information from.
>> and finally the warning tells us that 28 observations are not represented in the plot because they have some NAs, missing values.

>>

Ok, let's visualize those penguins with ggplot2!

>>

The data we'll work with are measurements for three species of penguins in Palmer Archipelago: Chinstrap, Gentoo, and Adelie.

>>

The data are in the palmerpenguins package

>> So let's load the packages first
>> And then glimpse at the data. 
>> glimpse is a function that prints out the variables in the data frame, their types -- which we'll dig deeper into later in the course --, and the first few observations as comma separated values.

The data contains body measurements on three species of penguins, chinstrap, gentoo, and adelie. The bodu measurements include things like bill length and depth, flipper length, and body mass. We also know which island the penguin is on, their sec, and the year of data collection. There are a total of 8 columns, so 8 variables.

The output also shows that we have 344 rows, that is, we have data on 344 penguins.

>>

The plot shown here is our final goal. We'll plot bill length against bill depth, both measured in millimeters. We'll represent each penguin with a point, colored by their species. The species mappings are summarized in the legend of the plot. The plot also has a title, a subtitle, and a caption.

>>

And the code for the plot is shown on this slide. It looks like what we've seen before -- ggplot function to start with, then the data, the aesthetic mappings, the geom, and some other layers for labels and color palette. This is a lot of code at once though, so let's unpack it layer by layer.

>>

In other words, let's code out loud!

>>

We start with the 
>> ggplot function 
>> and indicate that we want to plot the penguins data frame. As a result, we get an empty canvas that we can paint our data on.

>>

Them we map bill depth to the x-axis 
>> we can see the x-axis indicates the variable name, its range, and a reasonable breakpoint

>>

Then we map bill length to the y-axis
>> we can see the y-axis mapped as well

>>

And finally
>> we add a geom layer -- a geom point, indicating that the data should be represented as points. There seems to be three clusters of points here, let's see what happens if we also ask that the points be colored by species.

>>

Since this requires mapping another variable to a new aesthetic of the plot, we do this in the aesthetic mappings
>> mapping color to species. Note that not only the points are colored, but we also gained a legend describing the mappings -- red points represent Adelie penguins, green Chinstrap, blue Gentoo.

>>

Now that the data we want to see on our plot is there, let's add some labels.

>> Let's set the title to Bill depth and length. Not a particularly informative title, but it's a good starting point. We do this in the labs function, passing it to the title argument as a character string denoted with quotes. You can use double or single quotes in R, sticking to the tidyverse style guide we'll use double quotes.

>>

Let's also add a subtitle

>> Again in the labs function, passing it to the subtitle argument.

>>

And let's fix up the x and y axis labels.

>> By default ggplot2 will use the variable names, but we can overwrite them by updating the x and y label of the plot, and using more human-friendly text like bill depth mm and bill length mm.

>>

And finally let's relabel the legend as well

>> We do this also in the labs function, passing the desired label to the color argument. Note that the name of the argument matches the aesthetic mapping.

>>

And finally in the labels

>> let's add a caption for the data source. This automatically gets placed below the plot.

>>

And before we finish up our plot we need to do one more thing -- use a discrete color scale that is designed to be perceived by viewers with common forms of color blindness. 

>> We do this in a new layer, a scale layer, using a pre-defined color palette called viridis. The underscore-d denotes we will use the discrete color scale in this palette. If you have red-green color vision deficiency up until this point some of the points on the plot may have been difficult to tell apart. The goal with this palette is to make sure all, or at least more, viewers can see the points as intended.

>>

Putting it altogether we have our plot

>>

The code

>>

And the narrative we built with each layer of the plot

>>

Before we wrap up this introduction to ggplot2, one quick note about argument names. It's common in R to omit the names of the first two arguments. In the ggplot function

>> these are data and mapping
>> So you'll commonly see me and others write ggplot code in the second way, omitting these argument names from the code.
