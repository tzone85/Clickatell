# Clickatell Assessment
<small>This markup will display beautifully when opened in any of the Jetbrains IDE's.
<br>
other IDE's or text editors may be used as well though</small>
## Questions
 1. Apart from an IDE, which other tools or IDE extensions do you use for developing software?
 
 2.	Describe the process you follow for writing a piece of code from requirements to delivery.
 
 3.	What tools do you use for testing the quality of your code and why?
 
 4.	What is the difference between the HTML and the DOM?
 
 5.	What are pipes in Angular? Give an example.
 
 6.	You have a static html web page with 10,000 mobile numbers. How would you go about changing the format of all mobile numbers?
 
 7.	You have an array with integers between 1 and 1,000,000. Some numbers appear more than once in the array. 
 Find and output the duplicated numbers.
 
 8.	Describe a JSON object that stores all the teams, match fixtures and match results of a FIFA World Cup.
 
 9.	Write a function that accepts a name then outputs the words of the Happy Birthday song, using a loop and condition statement.
 
 10. Describe the app file structure you would use for a scalable Angular application, containing all the relevant sections you would typically use. Show this in the form of a folder/file tree structure.
 
 
 ## Answers
 1. Depending on the type of project/app that's at hand. Is it cloud based or not. To get to some kind of conclusion, I'm going to assume we're not taking the serverless approach. I'd use the Docker engine for my environment set up, Git and bitbucket for codebase & repository, MariaDB for my Database, and use SQL Workbench for the client. Mongo could be another choice but I'm going to assume that RDBS is the best path for our app.
    For the API layer I'd use the Laravel based Lumen framework and write tests for my application as well. Use postman for testing. For the frontend I'd use Angular and make use of Angular Material or just bootstrap for mobile first approach. 
    Assuming we're using an Agile approach, breaking tasks down to stories and possibly sub-stories on Jira. Also making use of Jenkins or Team City for deployments.
    In terms of testing once again it depends on the kind of tools I'm using. e.g. if it's PHP, then making use of PHPUnit, PHPSpec with code coverage.
 
 2. It really depends on what I'm building, what scope of tools am I allowed to use (e.g. developing on top of legacy code, one would need to adapt and use tools that won't break the project), 
    and the timeframe constraints if any.
    
    So I'll use a general case whereby I'm to build a medium size application with a backend as well as a frontend. We're following the git-flow approach and developing towards the given specification.
    
    I'd start up by configuring my environment, using Docker. To ensure that my app runs consistently on different machines with possibly different operating systems as long as they get the correct image of the application.
    
    My next step would be to start with the DB design (using MariaDB with the SQL Workbench client) as specified by the specification but at the same time, enquiring with the BA where I feel that things could be improved. Not in an objecting manner but more
    of an enquiring manner as they might be aware of something that I might not be. Which might be the reason for the seamingly non-optimal design.
    
    The next step that I would take would be to build a RESTFull api using Lumen, as to not hit the database for every single call to the DB, as well as providing a security layer for the underlying data. Another way to circumvent hitting the DB for every call is by adding caching between the DB and the API.
    This is not a silver bullet, it depends on the app and if this is the best architecture style to follow. Write tests for these calls using postman
    Write documentation for the API using a Postman as well.
    
    As far as the frontend is concerned, I'd make use of Angular (latest version if it's a new project for example). Utilizing Angular Material to leverate of material designs mobile first approach. And Import libraries that will be applicable to the application,
    a very basic example being something like Angular Reactive forms. for example. Breaking down the design into logical reusable components.
    The nice thing about Angular is that it ships with tests already configured so you can add to these tests when writing your own but the configuration is already set up.
    
    As mentioned earlier, we're following the git-flow approach, so one would break down the requirements into features and build these features, have them go through the code reviews as continuously when these features pass review for them to be deployed to the next environment,
    staging. Before having an actual QA actually testing the feature, it's always a good idea to have automated tests that test if the new code has not introduced bugs to the bigger system at large. These are not always full proof or not always well written, hence the need for human intervention to be able to catch 
    those say logical bugs the tests could not detect. That's where the QA's can then start testing functionality related to that feature. Any conflicts, bugs or code optimizations that get brought forward from the code reviews or through testing, to be developed back in the Dev environment, leave clear and descriptive commit messages. 
    Also give clear discriptive pull request info of what the feature is supposed to do, then promote the changes once again
    for a code review as well as to be tested by a QA should it pass the review.
 
    