# Information Visualization - D3 Assignment

This first lab assignment for the Information Visualization course consists of two parts. In the first part you will walk through the preparation and installation and then follow a step-by-step introduction to create your first visualization using **D3.js**. For the second part of the assignment you will create your own, somewhat more complex, visualizations for which ***the result will count towards your final grade***. Before you continue, please check the following information and deadlines.

|  Teaching Assistants  | Name | E-mail |
| ---------------------------- | --------- | ------------|
| Teaching Assistant | Noureldien Hussein | nhussein@uva.nl |
| Teaching Assistant | Kirill Gavrilyuk | kgavrilyuk@uva.nl |

|  Group  | Deliverable | Deadline | How |
| ---------------------------- | --------- | ------------| ------ |
| Group A | D3.js Assignment (this)     | Wednesday June, 14th 08:59 CET  | Upload to Blackboard.
| Group B | D3.js Assignment (this)     | Wednesday June, 14th 12:59 CET  | Upload to Blackboard.

## Before Starting

Before we start creating our first visualization using D3.js, we recommend students to download a proper code editor that they are comfortable with for writing HTML, CSS and JavaScript. Some excellent choices we recommend include:

1. [SublimeText](http://www.sublimetext.com/3) (Windows, OS X, Linux)
2. [Atom](https://atom.io) (Windows, OS X, Linux)
3. [NotePad++](https://notepad-plus-plus.org) (Windows)

Students that choose SublimeText as their editor can have a look at the [package repository](https://packagecontrol.io/search/javascript), which contains some very useful plugins for writing JavaScript code. After installing your code editor, we also recommend setting up a *version control system* such as Git. This is optional but highly recommended as you will later work together on the same code. Students unfamiliar with Git can walk through this [short introduction](https://try.github.io/) to Git.

For this course we only support Google Chrome as a browser as it is easier to debug JavaScript. However, when using **Google Chrome** as a browser you might encounter problems with loading local files from disk. By default Google Chrome does not allow reading local files from disk due to security reasons. Since we will use D3 to read datasets (e.g., CSV files) from disk we need to disable this security. We can start Chrome by passing the command line parameter `--allow-file-access-from-files`. Please use the following commands for starting Chrome from the command line, or have a look at the [documentation page](https://www.chromium.org/for-testers/command-line-flags):

```bash
chrome.exe --allow-file-access-from-files                                (for Windows)
open -a Google\ Chrome --args --allow-file-access-from-files             (for Mac OS X)
google-chrome --args --allow-file-access-from-files                      (for Linux)
```

For this and the next assignments you will write JavaScript code, and you will most likely run into problems at some point. A common problem is just a blank page when you are trying to view your visualization in the browser. When this happens you will have to debug your JavaScript code, which can be a little tricky sometimes due to limited or vague error messages. We recommend having a look at this StackOverflow question on **[debugging Javascript](http://stackoverflow.com/questions/988363/how-can-i-debug-my-javascript-code)**. It will be useful to always have the *Chrome Developer Console* open by pressing `Ctrl+Shift+J` and adding `console.log()` lines to your code to print intermediate results. Note that if you forget to start Chrome using the `--allow-file-access-from-files` parameter you will see an error similar to this one in the Developer Console.

```
d3.v3.min.js:1 XMLHttpRequest cannot load file:///.../cbs_companies_in_netherlands.csv. Cross origin requests are only supported for protocol schemes: http, data, chrome, chrome-extension, https, chrome-extension-resource.
```

### D3.js Visualization Library

**[D3.js](https://d3js.org/)** is a JavaScript library for producing interactive data visualizations in the browser. The library is built for being very flexible and allows for creating highly complex and visually pleasing graphs, bar charts and animated data visualizations. One of its primary advantages over other visualization libraries is the possibility to use all the modern web techniques such as SVG, HTML5 and CSS.

During this course we will use D3.js 4.0 which was introduced in 2016. If you are more familiar with D3.js 3.0, please, check the [list of changes](https://github.com/d3/d3/blob/master/CHANGES.md) or this [overview of changes](https://iros.github.io/d3-v4-whats-new/#1).   

The visualizations you will create all exist within the browser and are built using **[scalable vector graphics](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics)** (SVG). D3.js uses JavaScript functions to select elements, create other elements, perform styling and add animations. In addition, users can easily add their own styling or more complex visualizations using CSS and JavaScript. Central principle when using D3.js is a selection of elements from the **[Document Object Model](https://en.wikipedia.org/wiki/Document_Object_Model)** (DOM) on the page and the ability to modify them using operators similar to those used in **[jQuery](https://jquery.com/)**. For example, by using D3.js we can easily select all the rectangles `<rect>` on a page, change their fill color to magenta and update the position:

```javascript
 d3.selectAll("rect")         // select all <rect> elements
   .style("color", "magenta") // set style "color" to value "magenta"
   .attr("x", 100);           // set attribute "x" (horizontal position) to value 100px
   .attr("y", 0);             // set attribute "y" (vertical position) to value 0px
```

This example shows how we can select and modify elements based on the *type* (rectangle), but elements can also be selected based on their *class*, *identifier* or *attribute*. These selectors are by far the most common way in D3.js to manipulate elements on the page. We will now continue with a walkthrough in which you will create a simple bar chart.

## Walkthrough: Creating a Simple Bar Chart

In this walkthrough example we are going to create a simple bar chart displaying the percentage of never married people in the United States of America. This data is publicly available by the [FiveThirtyEight](https://github.com/fivethirtyeight/data/tree/master/marriage). We have specially prepared a dataset for you from `both_sexes.csv` to have information only about the population of 25-34 age. If you are interested in other datasets you can have a look at their webpage [FiveThirtyEight](https://fivethirtyeight.com/). The bar chart you will create looks similar to the following figure.

![Barchart](https://github.com/kgavrilyuk/UvA-InfoVis-2017-Students/blob/master/assets/barchart.png)

The first thing we need to do is setting up an empty HTML document which will hold all the code for our visualization. If you are familiar with HTML then you will immediately recognize all the components; if not, you might want to study all the elements in the document. Create an empty document with the name `barchart.html` and put the following code inside it.

```html
<!DOCTYPE html>
<meta charset="utf-8">

<!-- The visual styling of our barchart is in this file -->
<link rel="stylesheet" href="barchart.css">

<body>

<!-- We include D3 from an external location so that we don't have
       to download it and we are sure we are using the latest version.
       You can also dounload D3 file and put it into the same directory. -->
<script src="https://d3js.org/d3.v4.min.js"></script>

<script>
  // Here we are going to create a barchart using D3
  // ...
</script>
```

As you can see in `Line 5` a CSS stylesheet is included. The file `barchart.css` contains all the visual styling for the chart you will create. In addition to the HTML file you just created, also create a file `barchart.css` in the same directory and then put the following style elements inside. Study the style attributes for each of the elements as you will use them later.

```css
body {
  font: 10px sans-serif;
  padding: 40px 60px;
}

rect.bar {
  opacity: 0.7
}

rect.bar:hover {
  opacity: 1.0;
}

text.label {
  fill: #FFFFFF;
  font: 10px sans-serif;
}
}
```

If you open `barchart.html` in your browser at this point you will just see a blank page because we did not add any elements to the page. Now that we have a placeholder and styling for the chart, we continue by downloading the dataset that we will use for the visualization. The dataset is available in **[comma separated value](https://en.wikipedia.org/wiki/Comma-separated_values)** (CSV) format in `datasets` directory and in Blackboard under the name `marriage.csv`. Please download the dataset and put it in the `datasets` directory. As you study the contents of the dataset file, you will see that it contains the percentage of never married in the United States of America from 1960 till 2012. For this simple walkthrough we will only use the information about all people (`all`) independent of the level of education, wealth, location or ethnic group. You will use the columns denoting the wealth later in this assignment.

We are now going to set up the bar chart, *e.g.* the dimensions, location, axes of the figure. This is the first D3.js code that we will add to the document. Please include the following initialization code inside the empty `<script></script>` tags of `barchart.html`. Also, study the code and the comments carefully as this defines the main appearance of our bar chart. In particular, note how we define variables for the dimensions of the graph (`width`, `height`) to reuse them later for dynamically modifying the chart. Note the scalings for the axes, for different datasets you might need to change the scalings accordingly.

```javascript
// Define the size of the visualization
var margin = {top: 20, right: 20, bottom: 100, left: 60},
    width = 800 - margin.left - margin.right,
    height = 500 - margin.top - margin.bottom;

// Scaling on x-axis is 'band'. Band scales are like ordinal
// scales except the output range is continuous and numeric.
// Discrete output values are automatically computed
// by the scale by dividing the continuous range into uniform bands.
// Band scales are typically used for bar charts with an ordinal or categorical dimension.
var x = d3.scaleBand()
          .range([0, width])
          .padding(0.1);

// Scaling on y-axis is 'linear'
var y = d3.scaleLinear()
          .range([height, 0]);

// Set color scheme. Check https://github.com/d3/d3-scale#schemeCategory10
// for color schemes.          
var c10 = d3.scaleOrdinal(d3.schemeCategory10);

// Append the svg object to the body of the page. Then append
// a 'group' element to 'svg', moves the 'group' element to the top left margin.
var svg = d3.select("body").append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom)
    .attr("transform", "translate(" + margin.left + "," + margin.top + ")")
    .style("padding", "60px")
    .append("g")
      .attr("transform",
          "translate(" + margin.left + "," + margin.top + ")");

```

Although we have setup the bar chart, there is still nothing to show if you view the file in your browser. Next, we are going to load the dataset and complete the bar chart based on the data. Since our data is formatted as CSV, we can use the convenient `d3.csv` reader to load it. Below the code you have just added, paste and study the following code:

```javascript
// Here we define the path to the .csv file we are going to load.
// Note that this assumes that the dataset file is in the datasets directory
var csv_file = "../datasets/marriage.csv";
d3.csv(csv_file, function(error, data) {

    // Everything that uses the data will be inside this callback function.
    // Within this function, you can use the variable 'data' to access the contents of the CSV file.
    // More information on loading data files: https://github.com/d3/d3/wiki/CSV

});
```

Now that we have loaded the dataset we can use it to append components to the bar chart based on the data. The following large chunk of code will format the data, map the data to the x/y-axes and add the bars with appropriate height based on the data. Please paste the code inside the callback function you have just added and closely study the comments inline. This is also the final piece of code we need, everything that is necessary for our bar chart is here, so make sure you understand what is going on and view the chart in the browser.

```javascript
  // Check if an error occured while loading the data
  if (error) throw error;

    // Data formatting. Here we select the columns from the CSV file that we are
    // going to use. For our simple bar chart we only use the 'year' and 'all' columns.
    data.forEach(function(d) {
      d.year   =  d["year"] // read as string
      d.all  = +d["all"] * 100    // the plus (+) indicates converting to a number
    });

    // Scale the range of the data in the domains
    x.domain(data.map(function(d) { return d.year; }));
    y.domain([0, d3.max(data, function(d) { return d.all; })]);

    // Append the rectangles for the bar chart
    svg.selectAll(".bar")
        .data(data)
      .enter().append("rect")
        .attr("class", "bar")
        .attr("x", function(d) { return x(d.year); })
        .attr("width", x.bandwidth())
        .attr("y", function(d) { return y(d.all); })
        .attr("height", function(d) { return height - y(d.all); })
        .attr("fill", c10(0));

    // Add text inside the bars to display the percentage of never married people
    svg.selectAll("text")
        .data(data)
      .enter().append("text")
        .attr("class", "label")
        .attr("x", function(d) { return x(d.year) + 5; })
        .attr("y", function(d) { return y(d.all) + 10; })
        .attr("dy", ".5em")
        .text(function(d) { return d3.format(".2f")(d.all); });

    // Show the x-axis
    svg.append("g")
        .attr("transform", "translate(0," + height + ")")
        .call(d3.axisBottom(x));

    // Show the y-axis
    svg.append("g")
        .call(d3.axisLeft(y)
          .ticks(10)
          .tickFormat(d3.format(".2f")));

    // Add axis labels to the chart (Note: these are not built-in to D3)
    // Label x-axis
    svg.append("text")
      .attr("x", width / 2.0)
      .attr("y", height + 50)
      .style("font-weight", "bold")
      .style("font-size", "14px")
      .text("Year");

    // Label y-axis
    svg.append("text")
      .attr("y", -50)
      .attr("x", -height / 2.0 - 100)
      .attr("transform", "rotate(-90)")
      .style("font-weight", "bold")
      .style("font-size", "14px")
      .text("Percentage of never married")

    // Add a title to the chart (Note: these are not built-in to D3)
    svg.append("text")
      .attr("x", (width / 2.0 - 250))
      .attr("y", -20)
      .style("font-weight", "bold")
      .style("font-size", "22px")
      .text("Percentage of never married in the USA (age 25-34)");
```

We have reached the end of the walkthrough. You can find all code of walkthrough in the `code` directory. By now you should have created your first bar chart and understand the basics of D3. Most of the things that we have seen in this walkthrough you will also need for the first assignment. Remember to check the Chrome developer console by pressing `Ctrl+Shift+J` if you run into problems: the errors and warnings there will probably point you in the right direction for debugging. This walkthrough was just to get you started using D3.js. You can now continue with the first assignment.

## Assignment Part I: Grouped Bar Chart

In this assignment, you are expected to create another simple chart, namely, grouped bar chart. Grouped bar charts are useful when visualizing multiple categories of your data simultaneously. The following figure shows how your grouped bar chart should look like.

![GroupedBarChart](https://github.com/kgavrilyuk/UvA-InfoVis-2017-Students/blob/master/assets/grouped_barchart.png)

In this assignment, you are going to work on the dataset that contains the percentage of never married in the United States from 1960 till 2012. The dataset is available in `datasets` directory and in Blackboard under the name `marriage.csv`.

Similar to the walkthrough example, you should first define your visual layout in a file called `groupedbarchart.css`. If you have grasped the idea of D3.js in the walkthrough, you will see that this one is very similar to a regular bar chart in implementation. In case you feel lost, we recommend you to check out examples on this [page](https://github.com/d3/d3/wiki/Gallery).

**Requirements:** The part is complete when it has met the following requirements:

1. It is written completely in D3.js
2. It loads and uses the data from the provided CSV file
3. Each period is represented by the grouped bars
4. Period labels appear below the bars
5. The size of each bar is computed dynamically using D3.js
6. Chart contains dynamically computed y-axis on the left
7. Chart contains dynamically computed x-axis on the bottom


## Assignment Part II: Sold Dwellings in the Netherlands

In the final part of the assignment, you will visualize the number of sold dwellings (i.e. houses) in the Netherlands. We want to show the number of sold dwellings by each dwelling type for the year 2016. You're advised to use a pie chart or donut chart, as it is suitable for visualizing percentages and shares. An example of output: two figures below. The dataset can be simply downloaded from this repository `/datasets/House_Price_Index_Dwellings.csv`. Additionally, you can have a look at the dataset on [cbs.nl](http://statline.cbs.nl/StatWeb/publication/?DM=SLEN&PA=81886ENG&D1=0-5&D2=a&D3=79-l&LA=EN&HDR=T&STB=G1,G2&VW=T).

The figure below represents an example of a pie chart, visualizing the aforementioned data.

![No. of Dwellings Sold in 2010 Pie](https://github.com/kgavrilyuk/UvA-InfoVis-2017-Students/blob/master/assets/sold_dwellings_by_type.png)

While the figure below represents an example of a donut chart, visualizing the aforementioned data.

![No. of Dwellings Sold in 2010 Donut](https://github.com/kgavrilyuk/UvA-InfoVis-2017-Students/blob/master/assets/sold_dwellings_by_type_donut.png)

**Requirements:** The part is complete when it has met the following requirements:

1. It is written completely in D3.js
2. It loads and uses the data from one of the provided CSV files
3. Contains proper labels where necessary
4. Presents the data in a visually appealing and useful way
5. Each section of the pie/donut chart represents one dwelling type
6. The size of these sections are in proportion to the percentages of the represented types
7. The total number of sold dwellings is shown, as well as the percentages.

## Handing-in the Assignment

The assignment is handed in using Blackboard. **Please, do not send the deliverables per e-mail, they will get lost.** The deadline for this assignment can be found in the table at the top of this document. When your assignment contains multiple files, please make and upload a ZIP archive file to Blackboard. Your deliverables should include at least the following:

1. A short description of the visualization technique
2. Visualization result
3. All the source code used to produce the visualization. The source code is better written and delivered in 3 files:
 - content `.html`
 - script `.js`
 - style `.css` (optional).

We should be able to open your visualization with a single click, i.e. open the HTML file in the browser (e.g. dataset file should be in place).

## References and Further Reading
1. [Dashing D3.js Tutorial](https://www.dashingd3js.com/table-of-contents)
2. [Scott Murray's D3 Tutorial](http://alignedleft.com/tutorials/d3/)
3. [D3 examples with code](https://github.com/d3/d3/wiki/Gallery)
4. [Introduction to D3.js](https://www.youtube.com/watch?v=8jvoTV54nXw) (YouTube Video)
5. [Mike Bostock’s blog](https://bost.ocks.org/mike/)
6. [D3 official documentation wiki](https://github.com/d3/d3/wiki)
7. [Overview of changes in D3 v4](https://iros.github.io/d3-v4-whats-new/#1)
8. [List of changes in D3 v4](https://github.com/d3/d3/blob/master/CHANGES.md)
9. [Getting Sublime 3 To Launch your HTML page in a Browser with a Key Combo](http://michaelcrump.net/getting-sublime-3-to-launch-your-html-page-in-a-browser-with-a-key-combo/)
 
