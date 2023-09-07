# Week 3 Assessment

## Setup
* Fork and Clone this repository
* Run `update-database` - let the instructors know if you run into any issues!

## Exercise (10 Points)
### Securing the Application (4 points)
* Use Secrets Managemnt to remove the database connection string from the application.
* So that we can see the full implmentation, include a screenshot below to show your `secrets.json` file

![image](https://github.com/Jeremy-Kimball/Mod4Week3_Assessment/assets/130601077/ac62be12-d942-4050-b868-7aba0c1a7292)

### Maintaining Current-User (6 points)

This application includes some starter code so that we could maintain a current user.  Review the Login and Logout code in the Home Controller, along with the Login and Logout buttons in the Home/Index.cshtml file.  Building on this pre-existing structure:
* Create a cookie that holds a key for "currentUser" when a user logs in.
* Delete that cookie when a user logs out.
* Add the value of "current user" to all views

## Questions (10 Points)

For the following questions, answer as if you are in an interview!
1. Describe one strategy you have used to maintain state in a web application. (2 points)\
>Using cookies, it allows you to have the client's browser store information locally, which you can then use to identify them and provide data from the same unique user's previous sessions.
2. How would you protect sensitive data that we need to store in our database - for example, passwords? (2 points)
>By hashing the data using one of many different hashing algorithms, like SHA256 , it can turn a password string into a string of meaningless characters, you can go above and beyond and salt the passwords which is adding an extra set of characters onto the password before hashing it. It will help to protect users with poor passwords from themselves :)
3. Describe 3 additional common security risks in web development. (make sure you discuss what you know about the risk, and if you know how to minimize the risk) (6 points)
      - **Sql Injection** - Sql injection is when a user inputs sql code that is not expecting into a form giving them access to to more data than intended. You can validate or sanitize user input to ensure that any unintended database information is unable to be accessed
      - **No limits to API rates** - having no limits on the rate at which an api can be accessed opens up the possibility of a few different issues. DDOS (Distributed denial of service) attacks, low performance, and high costs. It can be mitigated by implementing limits to the amount of requests users can make.
      - **Overposting** - overposting is when more data than intended is sent into a form, this could lead to a user being able to adjust additional properties for example a user might be able to change the date of their test submissions allowing them to always have their test submissions be on time, even if it was submitted late. It can be prevented with DTOs(Data Transfer Object) it is a model designed to take only the explicitly specified data from one layer of the application to another. 
