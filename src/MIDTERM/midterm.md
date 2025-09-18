# Big City Pollution Data
* Josephine Kinsey
* /pollution/

## Overview

I chose the "pollution" dataset because of my interests in environmental science and science communication. I think that working with this dataset could give me practice for working with similar data sets in the future, if that kind of work comes up. I also think that, on a broader scale, pollution is an important topic to discuss, especially for big cities because of the unfair impacts it has on certain communities. Addtionally, pollution is an important aspect of public health, which has rapidly become more politicized and divisive in recent years. 

<!-- The following given executable js codeblock that imports the one set of D3.js
modules that you will need to use for Date() object work. You will need to
remove the forward-slashes preceeding the backticks, since I needed to
eascape these characters within this block. -->
```js
const pollutionData = FileAttachment("./../data/midterm-options/pollution/pollution_data.csv").csv({typed:true})
```

<!-- Then, divide the notebook into meaningfully sections and subsections.
Use the following general scheme to revise as needed. -->

## Attach the data

<!-- In this section, be sure to make some small notes about the data and output it
in an executable js codeblock, so you can review it on the page interactively.
You can note its size, for instance, as well as any other notable insights
gleaned during your first glance.

Remember that this is a notebook, so you can treat it like one. `:-)` -->
Below is the pollution data, formatted in a very long and unorganized Array. We will group this data in the sections below by charatceristics that could be used to draw concluisons and discern patterns!

```js
pollutionData
```
### Notes on the Pollution Data

  * Remarks from the authors of the data
    * Exigency: Air pollution leads to "severe and immediate" impacts on the climate and ecosystem, leads to global warming and climate change
    * PM2.5 & NO2 are most common air pollutants that cause irreprable respiratory disease
    * Air polltuon affects rainfall and weather patterns
    * Spatio-Temporal Data: 54 cities and 731 days 
    * The study is an early stage effort to tackle the issue of air pollution and to provide data and a methodlogy that communities can build on.
  * What's should I focus on in the dataset?
    * I think I want to look at the number of people who are staying home vs. not staying home, as I think that thet amount of fossil fuels burned would be increased by the number of people commuting (with the exception of the use of public transport). 
    * I think I'm also interested in finding what the pollution levels are like depending on the region of the country that the state is in (for example, is pollution worse in the southeast or northwest?)
      * I could do this by creating a grouping (in a for loop?) based on latitude and longitude.


## Convert Dates

<!-- Convert the dates, which are strings, into Date() objects with your own custom
D3.js parser and any formatters. Discuss any particular choices to format the
date data in any new ways.

Again, be sure to output your newly transformed data in executable codeblocks
for easier verification and reviewing. -->
It is important to have dates that can be used within the dataset, as it can help us discern seasonal and yearly patterns of pollution. For example, maybe pollution levels skyrocket between November-January because people travel for the holidays, and without dates we may not see this trend.

Below is an example data point to verify that the dates were converted appropriately and to show what values are within each object.

```js
import {utcParse,utcFormat} from "d3-time-format";
```
```js
const dateFormatter = utcFormat("%a, %b, %d, %Y")
```

```js
let testObject = pollutionData[0]
```

```js
testObject
```

## Grouping #1 - Name of grouping here

<!-- Explain your plan to group the data in a particular way here, before you do so.
At least one of the groupings should use some variation of D3's `.rollup()`, so
you can count particular grouped properties.

Provide a procedure of your grouping plan in an ordered list before the codeblock:

1. Coding_Action_1
2. Coding_Action_2
3. ...

Again, be sure to output your newly transformed data in executable codeblocks
for easier verification and reviewing. -->
Here, I intend to group the data based on location. I'll be doing this for both groupings, but here it will be a d3.rollup so groups can be nested within larger groups. I will be doing a grouping that begins at the highest level with the "State" value, then "County" value, then lastly the "City" value. This will will allow me tp keep the data organized so I can easily navigate between what level of specificity I want.

Here is my procedure for creating code to chieve this:

1. Establish a "js codeblock".
2. Create a variable for the name of the resulting d3.rollup internmap.
3. Create the d3.rollup().
4. Make the skeleton of the d3.rollup.
5. Enter in the key/property I want to split the dataset into groupings of.

```js
const locationRussianDollInternMap = d3.rollup(
  pollutionData,
  (D)=> D.length,
  (d) => d.picksomething
    (d) => d.picksomething within the other something
)
```

## Grouping #2 - Name of grouping here

Explain your plan to group the data in a particular way here, before you do so.
At least one of the groupings should use some variation of D3's `.rollup()`, so
you can count particular grouped properties.

Provide a procedure of your grouping plan in an ordered list before the codeblock:

1. Coding_Action_1
2. Coding_Action_2
3. ...

Again, be sure to output your newly transformed data in executable codeblocks
for easier verification and reviewing.

## Reflection

Use the following prompt to guide your reflection about your data work:
"What 2-3 insights and 2-3 questions did you glean from your initial work
with the dataset?"

Use the PR-TEMPLATE prompts to reflect on the midterm experience.

```
