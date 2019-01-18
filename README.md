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
A refresher at OOP in NodeJs, database design, system architecture and microservices what you shouldn't be doing.
Making sure your nodejs api is scalable with microservices. 

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
`When building api's make sure there is a source of truth for not just one item but for multiple items.`
# TBC..
typescript
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
Having a clean database/s and everything being normalized (otherwise different things can be calling different items and the data can be unclear where it is coming from).

When building api's make sure there is a source of truth for not just one item but for multiple items.
Have meaningful tests, make sure your tests actually explain what they are doing.

Building in micro services: has a lot of advantages to fixing problems like these.

# What is a Microservice
A microservice is a single self-contained unit which, together with many others, makes up a large application. By splitting your app into small units every part of it is independently deployable and scalable, can be written by different teams and in different programming languages and can be tested individually. — Max Stoiber

# Advantages

Everything is decoupled, making everything easier to find.

Microservices are deployable independently.

Easier to do weekly builds if not daily.

Deployments is less of a big deal because the microservice is in isolation meaning low chances of surfacing bugs.

Logs can be set to relate to each microservice making debugging a lot easier.

Microservices are easy to re-use than expanding larger codebases. 

Allows more flexibility in changing technologies.

Databases/tables can be split up based upon microservice, making api and database correspond smoothly.

Performance can be improved.

Less space necessary as each microservice is packaged up.

Its easy to have completely different technolodgy stacks in microservice's which could lead to massive performance improvements.

Easy to document in README's what each microservice does.




# Example 
  
An example of this could be: cat (mysql actions + resulting in json) could be split into npm package so when you need to make changes to it, it's in isolation and you are not having to change cat related items in multiple locations. 


This could be done in a number of ways but for this tutorial we are doing it in a npm package. (these can be public / private).

# Advantages
Cat will be isolation and will not need to change animal in multiple places.

TODO: `add call to cat and add mysql stuff in`
1. `create a new nodejs project in isolation`
2. `get old project to call new codebase.`
3. `split new project into calls Json you will need in animal.`

(mysql actions for catresult in json) could be split into npm package so when you need to make changes it, its in isolation and you are not having to change venue results in multiple locations.
Also making debugging easier etc. 


# Keep the structure simple

`/services
 /lib
 /routes
 `

# es8
I love ECMAScript don't get me wrong but used with bad architecture it can get messy real quick.
Here are some tools of ECMAScript you should be using right now:
# Classes, constructors, inheritence, 
# const, let
# promisify no more callback

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

