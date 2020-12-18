# Plotly
## Overview of Project
> Dana’s webpage and dynamic table are working as intended, but she’d like to provide a more in-depth analysis of UFO sightings by allowing users to filter for multiple criteria at the same time. In addition to the date, you’ll add table filters for the city, state, country, and shape. 

1. ***Deliverable 1***: Filter UFO sightings on multiple criteria
2. ***Deliverable 2***: A written report on the UFO analysis [`README.md`](https://github.com/emmanuelmartinezs/Ploty/). 

## Resources and Before Start Notes:

* Data Source: `ufo_starterCode.js` and `index.html`
* Data Tools: ECMAScript, JavaScript, Jupyter Notebook, Python and MongoDB
* Software: ES6+, ECMAScript, MongoDB, Python 3.8.3, Visual Studio Code 1.50.0

For more information, read the [`Documentation on JavaScript and other JS typess`](https://codeburst.io/javascript-double-equals-vs-triple-equals-61d4ce5a121a). 

## Overview of ES6+
ECMAScript, also referred to as "ES," is a scripting language designed to help standardize JavaScript. This means that ES provides guidelines and rules for JavaScript to follow, such as how a function should be created to run correctly, also known as the **proper syntax**.

Because ES has provided standardization for JavaScript, it also brings updates to the language. There are updates to every major coding language that fix bugs, update code, and provide overall quality of life improvements for the developers. ES6 is no exception!

There have been many updates to ES over the years, though the sixth update was a major one. You'll probably see "ES6+" mentioned out in the wild pretty often; this is a reference to the "big" update (ES6) as well as the later ones. It's also commonly known as "ES2015" or "ECMAScript 2015." (It was such an important update that it's even known by its year!) There are quite a few different ways to reference this language, but we'll be referring to it as ES6, JavaScript, or JS in this project.

## Benefits of the ES6 Update
We've briefly mentioned that the ES6 update was useful, but let's talk a bit more about why it was such a big deal.

Imagine two laptops, one old and one new, side by side. They're similar enough: they're close in size and shape and can complete many of the same tasks, but the newer laptop has an edge. It is faster and can perform tasks with greater efficiency than the older model.

JavaScript after the ES6 update is like the newer computer. This update included many updates to the syntax, which streamlined the code and made it easier to both read and write. Additional, quality of life improvements were implemented as well, such as adding Python-like generators and `for...of` loops. Even functions were updated and streamlined!

### NOTE:
> `for...of` loops is a new syntax associated with JavaScript, so it's okay to not be familiar with it yet! We'll discuss this syntax in more detail as we learn more about the language.

Later editions of ECMAScript brought about new additions as well, but they are for more advanced uses of the language. In this module, our focus will be on basic JavaScript and ES6 capabilities such as arrow functions. Both are still used today, and there's a chance you'll come up against older versions of JavaScript during interviews as well.


## JavaScript in the Real World
JavaScript is one of the powerhouse languages out in the wild today. While its strength is in creating visually appealing and dynamic content, it is starting to grow into other fields as well. Tensorflow, a popular machine learning tool, even has its own JavaScript library now.

It's pretty easy to start feeling daunted by everything JavaScript can do, so Dana is more interested in examples of similar websites—ones that use filters on lots of data.

* **Online shopping websites:** These are a great example of dynamic content. They contain filters for departments, and then filters for items within those departments. Filters on top of filters!
* **Ecological data:** [`DThe National Ecological Observatory Network (NEON)`](https://data.neonscience.org/browse-data?showAllDates=true&showAllSites=true&showTheme=org) has very large and diverse datasets; these are also displayed on their website as dynamic tables with multiple filters.
* **Weather data:** ([`The National Snow & Ice Data Center (NSIDC)`](https://nsidc.org/data/search/#keywords=permafrost/sortKeys=score,,desc/facetFilters=%257B%257D/pageNumber=1/itemsPerPage=25) also has very large datasets presented in table format on their website. These tables include filters and parameters that can be applied to their table.

## Writing JavaScript
One major component of each coding language is its syntax. For example, Python is a pretty clean and easy-to-read language; there aren't many semicolons, and the indentation and spacing makes sense. SQL, on the other hand, includes semicolons, but it also has guidelines and requirements when it comes to indentation and spacing.

JavaScript is no different: there are guidelines and requirements for writing it. But because JavaScript can be added to an HTML page, there are more guidelines and requirements than for languages that can only live in a .js file or Jupyter notebook such as Python. There are a few important things to remember about JavaScript syntax. We'll start with the following:

* Case sensitivity
* Semicolons
* Statements and expressions
* Code blocks

## Case Sensitivity
JavaScript is case sensitive. **Case sensitivity** means that JavaScript considers upper- and lower-case words to be different. For example, if we were to assign the words "data" and "Data" as variables, we would be able to save different information in each word. Of course, actually doing this with the word "data" could lead to confusion pretty quickly. Instead, just remember JavaScript cares about capital letters.

Similarly, JavaScript uses different naming conventions than Python that involve case sensitivity. Different languages utilize different methods to link words without using spaces, which is called a **case style**.

## Semicolons
Much like SQL, when coding in JavaScript it's good practice to end statements with a semicolon. Technically, they are optional when it comes to executing your code, but they are helpful because they tell JavaScript that a particular line or block of code is complete. It's considered a best practice to include semicolons throughout your code. You'll encounter many semicolons throughout this module.

Let's use a print statement as an example. In JavaScript, a print statement is called a **console log**. To print "Hello, world!" to the console, we would use this line:

````JS
// Printing a string with JavaScript
console.log("Hello, world!");
````

## Statements and Expressions
When describing JavaScript code, the terms "statements" and "expressions" are both used, and often. Here's how to distinguish between the two:

* Statements perform actions.
* Expressions create values.

Assigning a variable is an example of a statement. Using arithmetic to create a new value is an expression.

## Code Blocks
Code blocks, which we will see more often as we start writing functions, are denoted by curly brackets. Code inside the curly brackets are typically indented two to four spaces. This isn't required to run the code, but it does make reading it easier and follows the coding guidelines.

> Let's move on!

# Deliverable 1:  
## Filter UFO sightings on multiple criteria
### Deliverable Requirements:
Using JavaScript and HTML, you’ll modify the code in your `index.html` file to create more table filters. In addition to the date filter you created in this module, you’ll add filters for the city, state, country, and shape, as shown in the following image:

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/s1.png?raw=true)

Using JavaScript, you’ll replace the handleClick() function in your app.js file with a new function that saves the element, value, and id of the filter that was changed. Then, you’ll create a new function to loop through the dataset and keep only the results that match the search criteria. The webpage will be updated with the search criteria after pressing "Enter".


1. The list element that creates the button is removed, and there are five list elements for filtering in the `index.html` file. 
2. The event listener is modified to detect changes to each filter in the `app.js` file.
3. ​The `updateFilters()` function saves the element, value, and the id of the filter that was changed.
4. The filterTable() function loops through all of the filters and keeps any data that matches the filter values.
5. The webpage filters the table correctly based on user input.

 
### Results with detail analysis:

1. **The list element that creates the button is removed, and there are five list elements for filtering in the `index.html` file.**


> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````html
    <!--Filter and Table-->
    <div class="container-fluid">
        <div class="row">
          <div class="col-md-3">
                <form class="bg-dark">
                    <p>Filter Search</p>
                    <ul class="bg-dark">

                        <!-- CHALLENGE NEED - Filter Using New <form> Tag-->
                        <li class="list-group" class="btn-dark">
                                <label for="date">Enter Date</label>
                                <input type="text" placeholder="1/10/2010" id="datetime" />
                        </li>

                        <li class="list-group" class="btn-dark">
                            <label for="city">Enter City</label>
                            <input type="text" placeholder="benton" id="city">
                        </li>

                        <li class="list-group" class="btn-dark">
                            <label for="state">Enter State</label>
                            <input type="text" placeholder="ar" id="state">
                        </li>

                        <li class="list-group" class="btn-dark">
                            <label for="country">Enter Country</label>
                            <input type="text" placeholder="us" id="country">
                        </li>

                        <li class="list-group" class="btn-dark">
                            <label for="shape">Enter Shape</label>
                            <input type="text" placeholder="circle" id="shape">
                        </li>

                    </ul>
                </form>
          </div>


          <!--Dynamic Table-->
          <div class="col-md-9">
                <table class="table table-striped">
                <thead>
                        <tr>
                            <th>Date</th>
                            <th>City</th>
                            <th>State</th>
                            <th>Country</th>
                            <th>Shape</th>
                            <th>Duration</th>
                            <th>Comments</th>
                        </tr>
                </thead>
                <tbody></tbody>
                </table>
          </div>
````

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/1.1.JPG?raw=true)



2. **The event listener is modified to detect changes to each filter in the `app.js` file.**


> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````java
// 1. Create a variable to keep track of all the filters as an object.
var filters = {};

// 3. Use this function to update the filters. 
function updateFilters() {

    // 4a. Save the element that was changed as a variable.
    let inputElement = d3.select(this);
````

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/1.2.JPG?raw=true)



3. ​**The `updateFilters()` function saves the element, value, and the id of the filter that was changed.**


> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````java
function updateFilters() {

    // 4a. Save the element that was changed as a variable.
    let inputElement = d3.select(this);

    // 4b. Save the value that was changed as a variable.
    let inputValue = inputElement.property("value");

    // 4c. Save the id of the filter that was changed as a variable.
    let inputID = inputElement.attr("id");
````

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/1.3.JPG?raw=true)



4. **The `filterTable()` function loops through all of the filters and keeps any data that matches the filter values.**


> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````java
    // 5. If a filter value was entered then add that filterId and value
    // to the filters list. Otherwise, clear that filter from the filters object.

        if (inputValue) {
            filters[inputID] = inputValue;
        } else{filters ={};};
 
  
    // 6. Call function to apply all filters and rebuild the table
    filterTable(filters);
  
  }
````

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/1.4.JPG?raw=true)



5. **The webpage filters the table correctly based on user input.**


> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````java
  // 7. Use this function to filter the table when data is entered.
  function filterTable() {
  
    // 8. Set the filtered data to the tableData.
    let filteredData = tableData;
  
    // 9. Loop through all of the filters and keep any data that
    // matches the filter values
    Object.entries(obj).forEach(([fkey, fval]) =>{
        
      filteredData = filteredData.filter((row) => row[fkey] === fval)
          

  });  
  
    // 10. Finally, rebuild the table using the filtered data
    buildTable(filteredData); 
  }
````

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/1.5.JPG?raw=true)



# Deliverable 2: 
## A written report on the UFO analysis
### Deliverable Requirements:
For your written analysis, be sure to use complete and coherent sentences. Your written analysis should contain three sections, which cover the following:

1. **Overview of Project:** Explain the purpose of this analysis. 
2. **Results:** Describe to Dana how someone might use the new webpage by walking her through the process of using the search criteria. Use images of your webpage during the filtering process to support your explanation.
3. **​Summary:** In a summary statement, describe one drawback of this new design and two recommendations for further development.


 
### Results with detail analysis:


1. **Overview of Project:** Our UFOs Project has a single mission, and is to enhance our webpage with capability adding filters with multiple factors.
D3 functionality makes an instance listener for multiple changes in our search, displaying needed datasets on the result table.

> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````java
// EXTRA: Create a variable to keep track of all the filters as an object.
var clearEntries = d3.select("#clear-btn");
clearEntries.on("click", function() {
  location.reload();
});



// 1. Create a variable to keep track of all the filters as an object.
var filters = {
};

// 3. Use this function to update the filters. 
function updateFilters() {

    // 4a. Save the element that was changed as a variable.
    let inputElement = d3.select(this);

    // 4b. Save the value that was changed as a variable.
    let inputValue = inputElement.property("value");

    // 4c. Save the id of the filter that was changed as a variable.
    let inputID = inputElement.attr("id");
  
    // 5. If a filter value was entered then add that filterId and value
    // to the filters list. Otherwise, clear that filter from the filters object.

      if (inputValue) {
        filters[inputID] = inputValue;
    } else{filters ={};};
  
  
    // 6. Call function to apply all filters and rebuild the table
    filterTable(filters);
};

// 7. Use this function to filter the table when data is entered.
function filterTable(obj) {
  
    // 8. Set the filtered data to the tableData.
    let filteredData = tableData;
  
    // 9. Loop through all of the filters and keep any data that
    // matches the filter values
    Object.entries(obj).forEach(([fkey, fval]) =>{
        
      filteredData = filteredData.filter((row) => row[fkey] === fval)
          

  });
  
    // 10. Finally, rebuild the table using the filtered data
    buildTable(filteredData);
};
  
  // 2. Attach an event to listen for changes to each filter
  d3.selectAll("input").on("change",updateFilters);
  
  // Build the table when the page loads
  buildTable(tableData);
````

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/2.1.JPG?raw=true)



2. **Results:** Let’s describe step by step how someone might use the new webpage by walking through the process of using the search criteria. Using images of your webpage during the filtering process to support your explanation.
 
Let’s begin reviewing our HTML Filter and Table code. 

> Image with `JavaScript` & `HTML` Code below.

**Code and Image**


````html
    <!--Filter and Table-->
    <div class="container-fluid">
        <div class="row">
          <div class="col-md-3">
                <form class="bg-dark">
                    <p><b><u>FILTER SEARCH</u></b></p>
                    <ul class="bg-dark">

                        <!-- CHALLENGE NEED - Filter Using New <form> Tag-->
                        <li class="list-group" class="btn-dark">
                                <label for="datetime">Enter Date</label>
                                <input type="text" placeholder="1/10/2010" id="datetime" />
                        </li>

                        <li class="list-group" class="btn-dark">
                            <label for="city">Enter City</label>
                            <input type="text" placeholder="benton" id="city">
                        </li>

                        <li class="list-group" class="btn-dark">
                            <label for="state">Enter State</label>
                            <input type="text" placeholder="ar" id="state">
                        </li>

                        <li class="list-group" class="btn-dark">
                            <label for="country">Enter Country</label>
                            <input type="text" placeholder="us" id="country">
                        </li>

                        <li class="list-group" class="btn-dark">
                            <label for="shape">Enter Shape</label>
                            <input type="text" placeholder="circle" id="shape">
                        </li>
                        
                        <li class="list-group" class="btn-dark">
                            <button id="filter-btn" type="button" class="btn-dark">
                            Filter Table
                            </button>

                            <button id="clear-btn" type="button" class="btn-dark">
                            Clear Table
                            </button>

                        </li>

                    </ul>
                </form>
          </div>
````

From our Website (Project Example:) [`https://www.UFOs.gov`](https://emmanuelmartinezs.github.io/UFOs/). 


![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/W1.JPG?raw=true)

Need to visit FILTER SEARCH 

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/W2.JPG?raw=true)

On filter criteria, you can search by "Shape" only if want, example: triangle

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/W3.JPG?raw=true)

And click on "Filter Table" button,

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/W4.JPG?raw=true)

Automatically your search criteria will appear in our dynamic table resource.  

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/W5.JPG?raw=true)

And, if want to start a new search, just click on "Clear Table" button, and start a new search.

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/W6.JPG?raw=true)

After clear table, you may see our default data, 

![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/W7.JPG?raw=true)



3. ​**​Summary:** In a summary statement, describe one drawback of this new design and two recommendations for further development.


> Drawback:

During the project we realized that we needed to publicly expose the information, so it was necessary to use GitHub Pages to bring everything in one place.

> Recommendations:


1. **GitHub Pages - Website Presentation**
Please use the following [`GitHub Pages`](https://pages.github.com/), for more information on how to use IO pages. 

2. **Create a better `HTML`, `CSS`, and `JavaScript` Work interaction that feed UFOs data from most concise and automate workload**

For our best data presentation and most concise introduction to UFO information, we highly recommend UFO summaries. These fact-filled summaries provide revealing UFO information from dozens of government, military, and intelligence witnesses with impeccable credentials, that involves M.D. and former ER director, Dr. Steven M. Greer, has compiled videotaped testimony of astronauts, generals, professors, and highly respected government officials who reveal their direct experiences in the UFO cover-up. 

Including live testimonies were transcribed and published in the highly revealing Data. 



# Deliverable 3 (EXTRA): 
## UFOs IO Page on GitHub

Hope you enjoy the site.


> Image with `JavaScript` & `HTML` Code below.


![name-of-you-image](https://github.com/emmanuelmartinezs/UFOs/blob/main/Resources/Images/IO_Page.JPG?raw=true)

##### JavaScript, Bootstrap, and UFOs Analysis Completed by Emmanuel Martinez
