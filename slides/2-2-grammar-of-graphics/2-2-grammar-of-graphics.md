We're building our experience making plots with ggplot2. In this video we'll overview the theory underlying it all 

>>

the grammar of graphics.

>>

The grammar of graphics is a tool that enables us to concisely describe the components of a graphic
The ggplot2 package, which is part of tidyverse, implements the grammar of graphics in R

>>

With ggplot2, you can create a wide variety of plots layer-by-layer:

These layers are data, then aesthetics, then geoms, then facets, then statistics, then coordinates, and finally themes.

>>

Let's start with Layer 1: data

>>

The data layer is the foundation of the plot that gives you the canvas on which you can “paint” your data.

A neat feature of ggplot2 code is that each layer results in a valid plot, even if it's an "empty" plot like the one here.

>>

Layer 2 is aesthetics. We'll spend a bit of time on these.

>>

Aesthetics are characteristics of plotting characters that can be mapped to a specific variable in the data. For example color, or shape, or size, or alpha, in other words the transparency. There are many more aesthetic mappings, but we'll start with these.


