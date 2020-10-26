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
    In terms of testing once again it depends on the kind of tools I'm using. e.g. if it's PHP, then making use of PHPUnit, PHPSpec with code coverage. As well as making use of the PHPDoc DSL for assisting with the generation of the documentation.
    Wakatime is an excellent tool especially when working on multiple projects. For it tells you the amount of time spent on each project, when can come in handy when it comes to time for logging the time spent on each project for stakeholders or for billing clients.
 
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
    Also give clear descriptive pull request info of what the feature is supposed to do, then promote the changes once again
    for a code review as well as to be tested by a QA should it pass the review. One also updates the status on Jira for clear visibility as to where within the development cycle certain features are at. This transparency serves well for maybe non technically inclined stakeholders that need to know how far along in the process certain deliverables are at.
    While coding it's good to make use of well formatted DocBlocks to assist with the documentation of your code. In the same breath, after submitting your feature for review, it's good to start with the documentation of that feature to your Wiki as this tends to be "forgotten" when left to the very end of a project. Or there might not be enough time for it, which might influence the quality. 
    It's sometimes good to have auto-deployment scripts running and promote the code base to the next environment, e.g. from Dev -> Staging -> Pre-Production -> Production (Some companies have pre-production), but have well scheduled production deployments and not haphazard deployments to production for say every merge to the master branch.
    
 3. Once agian it is dependent but I'm going to draw a scenario as well.
    For me, first and formost is linting, and my IDE/Text editor helps a lot with that. This saves a lot of time and can be rather efficient. 
    Writing loggers, as you develop, to show where along the process you are. These help a lot when debugging and looking at the stack trace to see where in the process the failure took place.
    Exception handling, for when an unexpected result has been received. Using tools like PHPUnit, PHPSpec with code coverage are also great tools to use to ensure that your code is well tested, and how much of your code actually has tests as well.
    On the front end, depending on the framework one is using, I'm going to refer to adding to Angulars tests that it ships with. As these are already configured within your application. For setting up tests from scratch can be a tedious preocess. This once again can come in handy esp if you are under pressure for time.
    
 4. HTML (HyperText Markup Language) is basically a markup language. It's what gets returned from the server when a page is requested.
    The DOM (Document Object Model) is the tree representation of the markup language, that is represented on the browser.
    
 5. Angular pipes is usually a way to transform the way some values or data appears, to some desired way. This is usually done on the template. There's a few kinds of pipes that come standard with Angular. But one has the option to create new ones as well.
    ### Uppercase and lowercase:
        const someValue = 'The Nile River';
        <p>In Uppercase: {{ someValue | lowercase }}</p>
        <!-- output 'THE NILE RIVER' -->
        <p>In Lowerrcase: {{ someValue | uppercase }}</p>
        <!-- output 'the nile river' -->
        
    ### Date pipe:
        const dateValue = new Date('2020-09-01');
        <p>Birthdate: {{ dateValue | date : 'dd/MM/YYYY' }}</p>
        <!-- output '01/09/2020' -->
                 
 6. I'd write a small program with PHP, where I'd consume the HTML document, take its contents and convert it into an array 
    I would write a small PHP script, making use of preg_replace with a regular expression that specifies the required format for the phone numbers.
    This might require a little more time than maybe injecting php code within the HTML template, but this is much more future-proof and can be tweeked a little should the users needs change, and convert such data in batches if maybe it comes from the client's legacy services in that format. And say for some reason it would take them too long to convert it to a better format.  
    
 7. Given that it was mentioned that these questions would be a little vague, I'm going to try to make some assumptions just to help me better try to implement a possible solution.
    I'm going to assume that the data is unsorted within this array and that we have relatively powerful machines for the processing of the data.
     - Sort the array by utilizing the merge sort algorithm. I'm choosing this algorithm as it performs relatively well under its worst case scenario, with a Big O complexity of n*log(n). Given that we're not clear as to the size of the input. This tends to be the better choice than maybe bubble sort, with an O Notation of n^2 which won't serve us very well for larger data inputs.
     - Second big step would be to send traverse this sorted array, building a "dictionary" so to speak. Store each element in the dictionary but if the element already exists within the dictionary, store it in a separate data structure to be returned.
     
     #### Example
        const findRepeatInts = function(nums) {
            let set = new Set();
            for (let i = 0; i < nums.length; i++) {
                while (nums[i] !== i + 1) {
                    const j = nums[i] - 1;
                    if (nums[i] == nums[j]) {
                        set.add(nums[i]);
                        break;
                    } else if (nums[i] > nums.length) {
                        break;
                    }
                    [nums[i], nums[j]] = [nums[j], nums[i]];
                }
            }
         
            return Array.from(set);
        };
  
  8. I hope I understand this question properly. JSON's mostly used as a very user friendly way of communicating data from one system to another. A nice example of it's use case is on API's.
     
     ### Example
        {
            "success": true,
            "data": {
                    "fixtures": [
                        {
                            "id": "7343770",
                            "date": "2020-10-15",
                            "time": "17:00:00",
                            "round": "R78",
                            "home_name": "The Magicians",
                            "away_name": "Bad Boys",
                            "location": "",
                            "league_id": "313",
                            "competition_id": "257",
                            "home_id": "83",
                            "away_id": "82",
                            "competition": {
                                "id": "157",
                                "name": "Fifa World Cup"
                            },
                            "league": {
                                "id": "512",
                                "name": "Fifa World Cup",
                                "country_id": "38"
                            }
                        },
                        {
                            "id": "2002807",
                            "date": "2020-10-15",
                            "time": "17:30:00",
                            "round": "R23",
                            "home_name": "Beatles",
                            "away_name": "Alens",
                            "location": "Nile River",
                            "league_id": "19",
                            "competition_id": "467",
                            "home_id": "52",
                            "away_id": "44",
                            "competition": {
                                "id": "157",
                                "name": "Fifa World Cup"
                            },
                            "league": {
                                "id": "512",
                                "name": "Fifa World Cup",
                                "country_id": "1"
                            }
                        }
                     ],
                     "next_page": "https:\/\/livescore-api.com\/api-client\/fixtures\/matches.json?key=demo_key&secret=demo_secret&v=&page=2",
                     "prev_page": false
                    }
        }
        
 9. ### Code Sample
 
 
    const birthdaySong = (name) => {
            const repeat = 4;
            for (let i = 1; i <= repeat; i++) {
                if (i % 3 == 0) {
                    console.log('Happy birthday dear '+ name);
                } else {
                    console.log('Happy birthday to you');
                }
            }
        }
        
    birthdaySong("Thando");
    
 10. The app file structure. After generating say a new angular app. One would get a file structure similar to the following. <br>
     For files, viz, app-routing.modules.ts, app.component.html, app.component.scss, app.component.spec.ts, app.component.ts, app.modules.ts. This is out of the box. <br>
     When utilizing the ng generate CLI commands to generate your components. This is the directory they would be created in. And they themselves ship with the class, tests, styling as well as the template.
     
     #### app-routing.modules.ts
        This is where you route your application. Usually has a path in string format, as well as the component to forward to when that path is hit. You get to choose when creating new Angular app if you'd like to use routing for your project.
     #### app.component.html
        This is the templating of our component. One is able to write component based html which will be consistent for this component wherever it's used. 
     #### app.component.scss
        This is the styling that's related to the component as well. This will also ship with the component wherever it is used. You get to choose when creating new Angular app, if you'd like to use scss or css and you can choose whichever makes sense for your project.
     #### app.component.spec.ts
        This is your default configuration for writing your tests. For Angular, it's already set up, you can modify and add to this already built in configuration
     #### app.modules.ts
        This is where the class gets decorated with meta data basically. 
        Which is then made available to the rest of the application as well. This is where we'd also import additional modules. e.g. BrowserModule etc.
        This is also where our app module gets bootstrapped. We also add our services here as well.
        There's two kinds of imports that take place here. The ES6 and above level, i.e. the imports at the top of the file, and then the Angular ones mentioned above.
        
        
     