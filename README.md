# building-node-apis-that-scale-101

# Links
https://medium.com/@cramirez92/build-a-nodejs-cinema-microservice-and-deploying-it-with-docker-part-1-7e28e25bfa8b
https://blog.octo.com/en/clean-node-part-1/
https://flaviocopes.com/es2018/
https://github.com/lukehoban/es6features

# Background
I needed to explain to someone how to build scalable api's in nodeJs.

After searching the interwebs I was pretty surprised that there wasn't many articles about how to build clean, 
scalable api's in node.js. Which has led to this.

# Topics covered
OOP in nodejs, database design, system architecture and microservices.

Making sure your nodejs api is scalable. 

# Problems I have seen in node.js api's

# Monolithic structures 
Problems with this can include but not limited to:

No one wants to maintain it.

It's hard to understand what is going on.

They can be fragile.

And usually one or two people know most of it and if they left the company, the company would be screwed.

# Poorly treated databases
A database is extremely important to maintain.

Adding redundant tables and fields are detromental to building and maintaing a API. 

This causes uncertainity with developers as to which fields and tables to use.

# Sanity check your projects
# Database questions
`Are there redundancies?`

`Is the api grabbing blobs of data from the same field?`

`Is the database normalized?`

`Does every table need each other in the database or could it be seperate?`

`If you had to add 3-5 more tables would this be a problem? Would this be hard to address?`

# Testing
`Are the tests actually useful?`
`How is test coverage?`

`Do you have HTTP mock tests, do you need them?`
# TBC..
# Key considerations
Consider your programming roots of OOP and database design principles.
#
Some key practices for stopping these types of issues are from OOP, database design and system architecture. 

Use OOP standards
Inheritance, constructors, classes
  ``
    class dog {
    constructor(height) {
    this.height = height;
    }
    return this.height;
    }
    module.exports =(new dog());
    
    class animal {
    constructor() {
    let height = '20cm';
    }
    return this.dog(height)
    }
    module.exports =(new animal());
    
  ``
Having a clean database/s with non-redundant fields and tables, having normalized database/s (otherwise different things can be calling different items and the data can be unclear where it is coming from and appear in different columns).

When building api's make sure there is a source of truth for not just one item but for multiple items. 

Building in micro services: has a lot of advantages to fixing problems like these.

# What is a Microservice
A microservice is a single self-contained unit which, together with many others, makes up a large application. By splitting your app into small units every part of it is independently deployable and scalable, can be written by different teams and in different programming languages and can be tested individually. — Max Stoiber


Include making sure your code is scalable. 

An example of this could be: cat (mysql actions + resulting in json) could be split into npm package so when you need to make changes it, it's in isolation and you are not having to change cat related items in multiple locations. 

This also makes testings and debugging easier etc. 

# API
When building api's make sure there is a source of truth for not just one item but for multiple items.

  # Problem 
  
If cat became a really big part of our codebase and dog was hardly used. It might be time to split cat and dog up. 
Building in micro services has a lot of advantages to fixing problems like these.
  

This could be done in a number of ways but for this tutorial we are doing it in a npm package. (these can be public / private).

# Advantages
Cat will be isolation and will not need to change animal in multiple places.

TODO: `add call to cat and add mysql stuff in`
1. `create a new nodejs project in isolation`
2. `get old project to call new codebase.`
3. `split new project into calls Json you will need in animal.`

(mysql actions for catresult in json) could be split into npm package so when you need to make changes it, its in isolation and you are not having to change venue results in multiple locations.
Also making debugging easier etc. 


# Structure

`/services
 /lib
 /routes
 `

# es8
I love ECMAScript don't get me wrong but used with bad architecture it can get messy real quick.
Here are some tools of ECMAScript you should be using right now:
# Classes
``class cat {
    constructor(height) 
    {
      this.height = height;
    }
    return height;
}
  module.exports =(new cat());
``

There is obviously a lot more I could mentioned here but I think the most important things to remember when considering changes like this is it doesn't need to be done in one go it should happen over time and it should be designed out with your team.

