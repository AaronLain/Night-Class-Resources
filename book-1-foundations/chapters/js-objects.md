# Javascript Objects
Your job as a web application developer will often be to take a process that is done by an organization and build an application that does the same thing.

For example, a small company may use a colossal Excel spreadsheet to track all of their business expenses, and they email it around to each other, and eventually the accounting department gets it. They eventually realize that this process is rife with opportunities for human error, and the file becomes so large that it can't be emailed any more.

They hire you to build an application to track expenses.

Let's examine some of the things that you will be representing in code.

1. An employee who needs to track expenses
1. The expense itself (date, business, dollar amount, purpose, etc.)
1. An employee who needs to verify that it's a valid expense
1. An expense report

These things are objects we need to represent in code. Each object has properties that define it.

* An employee has a first name, last name, a role, and an account number
* The expense has a date, location, dollar amount, and purpose
* The expense report has a date, and a collection of expenses

So objects are things in the physical world that have properties that we want to represent in the application. A simple representation of an expense resource, in code, would look like this.

```js
const expense = {
    dateCreated: "01/01/2017",
    location: "Bob's Burgers",
    dollarAmount: "14.34",
    purpose: "Lunch with very important client",
    code: "1001A"
}
```

Here's a representation of a person who is an employee as a JavaScript object.

```js
const employee = {
    firstName: "Michael",
    lastName: "Tambornino",
    role: "Sales Rep",
    accountNumber: "1-8349058340"
}
```

Here's a representation of an expense report resource. It's a collection of expenses, with a timestamp of when the report was generated.

```js
const expenseReport = {
    dateCreated: "02/01/2017",
    expenses: [
        {
            amount: 14.34,
            dateCreated: "01/01/2017",
            vendor: "Bob's Burgers",
            code: "1001A"
        },
        {
            amount: 51.03,
            dateCreated: "01/03/2017",
            vendor: "Sunoco",
            code: "2213D"
        },
        {
            amount: 7.22,
            dateCreated: "01/07/2017",
            vendor: "Taco Bell",
            code: "1001A"
        }
    ]
}
```

## Object State

Ok, I mentioned "object state" above, and you might not understand what I mean by that. Stated as simply as possible, when you hear the words _object state_, it means that you want to know what the values of an object's properties are _**at this moment in time**_. That means an object's state can change, i.e. a property's value can be reassigned.

```js
const employee = {
    firstName: "Michael",
    lastName: "Tambornino",
    role: "Sales Rep",
    accountNumber: "1-8349058340"
}
```

Those property values define the __*initial state*__ of this employee that we're representing in code.

```js
employee.role = "Sales Manager"
```

I just changed the state of the JavaScript object that is representing Michael Tambornino.

## Challenge 1

You have volunteered your time to a local political candidate, Elizabeth Sanger, who wants to become a US representative in Congress for your district. Unfortunately, the team discovered that you're a software developer, so they have begged you to build an application that lets them track volunteers, and store information about Elizabeth and her campaign.

Your job is to define the different objects and arrays, their structure, and the corresponding properties for each, to represent the following information about Elizabeth's campaign.  All of these properties should live under a variable called `elizabethSanger`.  This variable should be equal to an object.

```js
let elizabethSanger = {
    // write all your properties here
}
```

1. Her congressional district (_you can use yours here_)
1. Her platform statements for the following issues.
    1. Taxes
    1. Jobs
    1. Infrastructure
    1. Health care
    1. Crime and enforcement
1. URL for donation form
1. Calendar of events
1. Volunteer information
    1. Name
    1. Address
    1. Email
    1. Phone number
    1. Availability
    1. What activities each one is willing to do (e.g. answering phone calls, taking polls, etc.)
1. Biography
1. Image gallery
    1. Head shot
    1. Picture of family
    1. Picture of constituents
1. Mission statement
1. URL for registering to vote

## Challenge 2
Once you have determined the data structure for the `elizabethSanger` object, its time to put all that stuff in the dom.  Write a `printToDom` function that takes in the string to print and the id of the div to print to.  Re-use that function as needed to print to the dom.

Create a function for each of the 9 properties above that builds up the string required to print this information to the dom.  Once the string is correct pass it and a divId to the printToDom function.  You will need to create 9 divs with unique ids in your index.html.  For example, create at `registerToVoteString` function this function should create an anchor tag that links to the URL for registering to vote property in the `elizabethSanger` object.

The platform statements, volunteer information, and image gallery properties should be arrays.  This means to display this information you will need to loop over the array to create the string.  We have not done this in class yet so give it your best shot.  Spoiler alert - you need a for loop in each function for these three.

## Challenge 3
Write a corresponding function for each of the eight properties whose purpose is to change the state of the object. Then use your functions to modify the existing data.

Things to think about.

- Am I modifying an array? Then the function argument should be added to the target array with the `push()` method.
- Am I modifying an object? Then I should pass both the key name to be modified, and its corresponding value.

This challenge is for you to practice writing functions, so the more you can write, the better. It helps make neural connections in your brain at this point since you're still building your software vocabulary.

Each of these functions should call the corresponding string creation function from part 2 so when the data is updated the DOM reflects the changes.
