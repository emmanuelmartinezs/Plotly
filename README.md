# Plotly
## Overview of Project
> Dana’s webpage and dynamic table are working as intended, but she’d like to provide a more in-depth analysis of UFO sightings by allowing users to filter for multiple criteria at the same time. In addition to the date, you’ll add table filters for the city, state, country, and shape. 

1. ***Deliverable 1***: Filter UFO sightings on multiple criteria
2. ***Deliverable 2***: A written report on the UFO analysis [`README.md`](https://github.com/emmanuelmartinezs/Ploty/). 

## Resources and Before Start Notes:

* Data Source: `ufo_starterCode.js` and `index.html`
* Data Tools: ECMAScript, JavaScript, Jupyter Notebook, Python and MongoDB
* Software: ES6+, ECMAScript, MongoDB, Python 3.8.3, Visual Studio Code 1.50.0

For more information, read the [`Documentation on Plotly.js Basic Charts`](https://plotly.com/javascript/basic-charts/). 
And for more information, read the [`CORS Documentation`](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS). 

## Overview of ES6+
ECMAScript, also referred to as "ES," is a scripting language designed to help standardize JavaScript. This means that ES provides guidelines and rules for JavaScript to follow, such as how a function should be created to run correctly, also known as the **proper syntax**.

Because ES has provided standardization for JavaScript, it also brings updates to the language. There are updates to every major coding language that fix bugs, update code, and provide overall quality of life improvements for the developers. ES6 is no exception!

There have been many updates to ES over the years, though the sixth update was a major one. You'll probably see "ES6+" mentioned out in the wild pretty often; this is a reference to the "big" update (ES6) as well as the later ones. It's also commonly known as "ES2015" or "ECMAScript 2015." (It was such an important update that it's even known by its year!) There are quite a few different ways to reference this language, but we'll be referring to it as ES6, JavaScript, or JS in this project.

## Benefits of the ES6 Update
We've briefly mentioned that the ES6 update was useful, but let's talk a bit more about why it was such a big deal.

Imagine two laptops, one old and one new, side by side. They're similar enough: they're close in size and shape and can complete many of the same tasks, but the newer laptop has an edge. It is faster and can perform tasks with greater efficiency than the older model.

JavaScript after the ES6 update is like the newer computer. This update included many updates to the syntax, which streamlined the code and made it easier to both read and write. Additional, quality of life improvements were implemented as well, such as adding Python-like generators and `for...of` loops. Even functions were updated and streamlined!

# Functional JavaScript

## The map() Method

The `map()` method in JavaScript applies a transformation to each element in an array. Like a for loop, it can perform an operation to every element of an array.

Here is an example in which all the numbers of an array are doubled:

````java
var numbers = [1,2,3,4,5];
var doubled = numbers.map(function(num){
    return num * 2;
});
console.log(doubled);
````

In this code, an array named `numbers` contains five integers:`var numbers = [1,2,3,4,5];`. Let's break down the rest of the code in more detail:

- The `numbers` array calls the `map()` method.
- Inside the `map()` method, there is another function. This function is anonymous, meaning that the function does not have a name. When `map()` is called, it in turn calls this anonymous function.
- The anonymous function takes a parameter, named `num`, and returns the number multiplied by 2. Its sole task is to perform this single action.
- For every element in the array, the `map()` method calls the anonymous function, which doubles the value of the element.
- The `map()` method returns an array of doubled values, which is assigned the variable `doubled`.

Here, the `map()` function becomes a method of the `numbers` array. It then takes in an anonymous function whose sole task is to double the value of num, its argument.

Behind the scenes, an iterative process similar to a `for` loop takes place. The anonymous function takes in each integer of the `numbers` array and doubles it. Finally, the variable `doubled` is an array of integers whose values are twice their original values.

Try running the code in your browser console and view the results for doubled. You should see the following:

![name-of-you-image](https://github.com/emmanuelmartinezs/Plotly/blob/main/Resources/Images/s1.png?raw=true)


## The filter() Method

Another functional programming technique is the `filter()` method. Like the map() method, it accepts another function as its parameter. Like `map()`, `filter()` performs an operation on every element in the original array. Unlike `map()`, however, `filter()` does not necessarily return an array whose length is the same as the original array.

Let's see what this means in an example. Run the following code in your console. What does `larger` return?

````java
var numbers = [1,2,3,4,5];

var larger = numbers.filter(function(num){
    return num > 1;
});

console.log(larger);
````

It returns an array of integers that are larger than 1: `[2,3,4,5]`.This example is remarkably similar to the last one, with one major difference.

First, the similarities:

- The `numbers` array uses the `filter()` method.
- The `filter()` method, in turn, takes an anonymous function as its argument. The anonymous function's sole task is to take in a parameter, called `num`.

The `filter()` method operates on each element of the `numbers` array. So how does it differ from `map()`?

The `map()` method transforms every element of the original array, and so the size of the transformed array is the same as that of the original array.

The `filter()` method, on the other hand, returns an array of values that meet certain criteria. Values in the original array that do not fulfill the condition are filtered out. In this case, specifically, the anonymous function called by `filter()` returns `true` if an argument is larger than 1, and false if it does not. The `filter()` method runs the anonymous function on every element of the original `numbers` array. Only numbers that are larger than 1 are returned: `[2,3,4,5]`. So whereas applying `map()` to the numbers array would have returned an array with five elements, applying this specific filter returned an array of only four elements.


## The Arrow Functions

Let's do a quick review of arrow functions. An arrow function in JavaScript is syntactic sugar. That is, an arrow function does the same thing as a standard JavaScript function, but it streamlines the syntax used to accomplish the same task.  

The anonymous function inside `map()` and `filter()` can be simplified as an arrow function. Here's an example:

````java
var numbers = [1,2,3,4,5];


var doubled = numbers.map(num => num * 2);
console.log(doubled);
````

The `map()` method performs the identical operation as before: it doubles each element in the `numbers` array. However, the anonymous function inside `map()` has been replaced by an arrow function. Contrast the two:

````java
var familyAge = [3,2,39,37,9];
var sortedAge = familyAge.sort((a,b) => a - b);
console.log(sortedAge);
````

`sortedAge` returns the array `[2,3,9,37,39]`. Like `map()` and `filter()`, `sort()` takes in an anonymous function. During each iteration, the anonymous function, an arrow function in this case, compares one element of the array `(a)` with another element in the array `(b)`. From `a`, it subtracts `b`. If the result is negative (i.e., `b` is larger than `a`) then it stays put. If the result of the subtraction is positive, the order of the two elements is reversed. Look at a modified version of this example.


## The slice() Method

Roza also needs to be able to select a subset of the data. In her project, for example, she might perform a transformation on an array, filter it, sort it, and then display only the top five results.

````java
var integers = [0,1,2,3,4,5];
var slice1 = integers.slice(0,2);
````

In this example, the `slice()` method returns the first two elements of the `integer` array: `[0,1]`. The first argument is the position of where to begin the selection. Here, it is at index position 0. The next argument, 2, denotes the position of the array where the slicing ceases. In other words, the `slice()` method begins selecting the array at index position 0, and stops right before reaching index position 2. So here, it returns elements at index positions 0 and 1, but not 2.

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
