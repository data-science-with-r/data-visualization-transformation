Hello. In this video, we will introduce data visualization and give an overview of the why and how of data visualization.

>>

But before we do so, let's formally introduce the idea of a dataset.

>>

There are two pieces of terminology that are important about data sets.

>> Each row is an observation and 
>> Each column is a variable 

>> Here, we're looking at a data set called Star Wars that contains information on characters from the Star Wars enterprise. Each row is a character, and each column is an attribute of that character. For example, the first row is Luke Skywalker. Let's take a quick closer look at his row.

>>

We know some things about Luke -- his name, his height, which is 172 centimeters; his weight is 77 kilograms; his hair color is blonde, we know his birth year, and so on. Additionally, some of the things we know about him are a single entry. For example, the eye color is blue, the skin color is fair, the species is human, etc. However, some of the other things are lists because he has multiple entries for that particular variable. For example, the films, the vehicles, and the starships he's been in. This course will focus on variables where we only have a single entry per observation, like height and weight, eye color, skin color, species, etc. Later in the specialization, we will talk more about list columns, where we have multiple entries per observation in a column. For now, let's set those aside since they require us to know a little bit more programming before we can wrangle and visualize them.

>>

A helpful function when you're getting started with a data set is the glimpse() function, which will not only report the number of rows and the number of columns in the data set but also give us a list of the columns. So, particularly if you have a wide data set with lots of columns, this is a great way to list all of them down a list. This view also tells us the types of columns. For example, chr stands for character, in for integer, dbl for double, etc. We'll discuss formal data types and classes later in the course. This output also shows us the first few observations in each variable, which is also helpful for getting a sense of the data.

>>

When you start analyzing a new dataset, the first questions you should ask are how many rows and columns this dataset has, what each row represents, and what each column represents. The data dictionary, or the data documentation, is a good place to find answers to these questions. This particular Star Wars dataset is distributed with an R package -- specifically, the dplyr package that we will introduce a bit more formally soon. Since it's distributed with a package, its documentation can be accessed just like documentation for any R function can be accessed, with a question mark followed by the name of the thing you want to learn more about. The documentation tells us something about the data overall and has descriptions for each of the variables.

I introduced one more new concept here -- a package. Packages are the fundamental units of reproducible R code. They include reusable R functions, the documentation that describes how to use them, and sample data. dplyr is one of the most popular R packages for data wrangling.

>>

Ok, back to Star Wars. How else can we answer these preliminary data questions, such as the number of rows and columns?

>> Some handy functions are nrow, col, and dim. They have pretty evocative names -- nrow for number of rows, ncol for number of columns, and dim for the dimensions of the dataset, where the output is first the number of rows then the number of columns. Note that in each case, the function name is followed by parentheses, and in the parentheses goes the name of the object you want to apply the function to. So we would articulate these as nrow of starwars -- 87 rows, ncol of starwars -- 14 columns, and dim of starwars -- 87 by 14.

>>

Now that we know a bit about how data frames are represented in R and how we can start looking into them, let's begin exploring them.

>>

Exploratory data analysis, commonly referred to as EDA, is an approach for analyzing data sets to summarize their main characteristics.

>> Often, this is visual -- this is what we'll focus on first
>> But we might also calculate summary statistics -- this is what we'll focus on next
>> And both visualization and summarization may require wrangling, manipulation, or transformation at (or before) this stage of the analysis

>>

Our first exploration is the mass and height of Star Wars characters. We want to answer the following questions: "How would you describe the relationship between mass and height of Star Wars characters? What other variables would help us understand data points that don't follow the overall trend? Who is the not-so-tall but really chubby character?"

To answer this question, let's look at a visualization of mass (on the y-axis) vs. height (on the x-axis). Usually, height and weight are positively associated for humans and animals, but the Star Wars enterprise has some non-human characters, like droids. And who knows how their heights and weights are associated?! So, while we can spot this positive association for most of the observations in the data, the overall trend is difficult to see because of the one extreme outlier, which squishes the rest of the data to the bottom of the plot.

So, who is this not-so-tall but really chubby character? If you are a Star Wars fan, you probably got this already, but even if you know very little about Star Wars, you'll recognize this little character.

>>

It turns out it's Jabba! Not so tall, but really really chubby. The data visualization helped us identify the observation that stands out from the rest, and some digging into the data revealed the observation.

>>

This quote from John Tukey, who wrote a bunch about exploratory data analysis, has a famous quote that's fitting here: "The simple graph has brought more information to the data analyst's mind than any other device."

>> Data visualization, an essential part of exploratory data analysis at a high level, is the creation and study of the visual representation of data
>> There are many tools for visualizing data – R is one of them
>> And within R, there are many approaches and systems for making data visualizations – ggplot2, yet another R package, is one of them, and that's what we're going to use 

>>

We'll get to the how soon, but let's briefly talk about why and why we visualize.

>>

Take a look at this dataset. It's a famous one called Anscombe's Quartet. Scrolling down, you can see four datasets stacked on top of each other, and each dataset has two variables, an x and a y. 

>> 

This next slide has a bunch of code you'll soon learn more about. But, in a nutshell, it calculates some summary statistics for each dataset. Let's focus on the output for now, not the code. What do you see? The means of x values for each dataset are the same. So are the means of y values. And the standard deviations. And even the correlation between the xs and ys for each dataset. Based on these summary statistics, how do you think these datasets compare? [PAUSE] They appear identical.

But let's not yet jump to conclusions and visualize the data first.

>>

Once again, focus on the output for now and not the code. [PAUSE] The scatterplots revealed something very different -- these datasets don't look similar at all!

>>

In case I haven't convinced you that visualization is a crucial part of exploratory analysis, here are two more examples. The first one comes from a survey where college students are asked how old they were when they had their first kiss. First, think about how you expect the distribution of their responses to look. 

>> Then, examine the plot. Do you see anything out of the ordinary? [PAUSE] Many of the responses are where I would expect them to be, but what about the answers in the much younger ages? This is likely an indication of a bad survey question -- some respondents must have interpreted the question as a romantic kiss while others as any kiss, like a kiss from a mom to a baby. If we had simply viewed summary statistics like mean age at first kiss, we would not be able to catch this data feature.

>>

Here is another one: The same group of students were asked how many times they visit Facebook daily. Once again, think about how you might expect the distribution of their responses to look.

>> Then, examine the plot. How are people reporting lower vs. higher values of FB visits? [PAUSE] Those reporting lower values seem to give precise answers, like three times a day or eight times a day, while those reporting higher values seem to provide rounded answers. This is yet another feature that wouldn't be identifiable from summary statistics, but a visualization makes it as clear as day.

Each of these examples was about why we visualize data. Next up is the "how".
