Hello, and welcome! My name is Mine Çetinkaya-Rundel, and I will be your instructor for the specialization titled Data Science with R. The first course in the specialization is Data visualization and transformation. Let's dive in!


>>

"Hello world" is often the first program beginners write, and since we'll be doing lots of coding in this course, we'll start with a hello world, too!

>>

But before we get there, let's talk about data science.

>> Data science is an exciting discipline that allows you to turn raw data into understanding, insight, and knowledge.
>> There are many ways and toolkits for doing data science. In this course, you'll learn to do data science the tidy way -- but more on what "tidy" means in this context later...
>> Specifically, this is a course that introduces you to data science, with an emphasis on statistical thinking.

>>

However, before we get to data science content, let's review some commonly asked questions. 

>> First question: What data science background does this course assume?
Answer: None. However, it does require a willingness to learn and a motivation to work with data.
>> Another question: Will we be doing computing? Oh yes!
>> What computing language will we learn? R!
>> Why not language X? Great question. There are many languages data scientists use. In fact, many data scientists use multiple languages, one for some parts of their data analysis and another for others. In this course, we've made the choice to stick with R!

>>

Let's talk a bit about software.

>>

Data organized in rows and columns in a spreadsheet program might be familiar to some of you. Spreadsheets are a ubiquitous tool for storing tabular data. Some people do data analysis for them as well. But we won't be doing that.

>>

Instead, we'll use R. This is what working in R looked like when I started learning R in graduate school. And, frankly, that looked intimidating.

>>

Nowadays, a large portion of people working in R use RStudio, which you will also learn in this course. The RStudio window might look foreign to you, but that's okay. We will walk through panes, how we use them, etc.

>>

So, we've said a bit about the software we'll use to conduct data analysis, but what does an end-to-end data analysis entail? Let's take a look.

>>

Here is the data science life cycle diagram from the book R for Data Science, which you'll be reading in this course. The diagram outlines many stages of data science.

>>

We start by importing data from a spreadsheet or a database or scraping it off the web.

>>

Then, reality strikes. You almost never get data that is perfectly pristine and organized precisely for the analysis you'll conduct, so you usually need to tidy it and transform it a bit to get it ready for analysis.

>>

We often start with exploratory analysis, which involves visualizing and summarizing.

>>

Then, you might apply modeling techniques to make inferences and predictions with your data.

>>

This will often reveal aspects of your data you want to address by transforming and visualizing it further. So, you spend some time in this cycle to understand your data.

>>

Either you get to a point where you're happy with your data analysis, or you hit a deadline, so finally, you need to communicate your results.

>>

Here is data from the Google Trend Index, which measures how popular specific search terms related to topics like travel, pictured here, are. We're seeing a cyclical, or seasonal, pattern for when travel-related search terms gain and lose popularity. This prompts us to return to the raw data, which has dates, create a new column for the season that we calculate based on these dates, and use that variable as an indicator in subsequent analyses. This is an example of how a visualization and some modeling results -- the red smooth curve overlaid on the visualization -- prompt further data transformation.

>>

Then, as I said, you either come to a deadline, analyze the data sufficiently, and communicate your results. But that feels like holding off on writing your term paper until the very last minute after "researching" for a long time, which is not a habit we want to promote. So, instead, we'll add the communication stage to our cycle of understanding the data, writing up our results, and analyzing the data. But we need a way to do this without too much context-switching. Therefore, we'll do our data analysis in computational notebooks, specifically Quarto documents, that allow you to write and run code and write your narrative in the same document.

>>

We can also see one more stage in the data cycle encapsulating everything else -- program. It's out there not because it's less important than the other stages but because it governs all of them. All of these stages require a little bit of programming.

>>

All of these stages together can take a considerable amount of time to learn. In the first course of our specialization, we'll focus primarily on the data visualization and transformation stages and tooling for doing data science with R.
