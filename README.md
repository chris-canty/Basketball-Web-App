The aim of this project is to develop a web-based application for managing a basketball team's games, players, and statistics. The motivation for choosing this application is that it provides an opportunity to learn about web development and database design while also catering to our teams’ personal interest in basketball. The key components of this project include the database design, front-end development, and back-end development. 

We will be displaying information for NCAA Division One schools in the state of Florida, such as FSU,UF, UCF, FAU, etc. In total we used data from thirteen different teams. For our database, we are going to display each team’s roster as well as each player’s name, height, weight, jersey number, and year. We will also allow for the addition and removal of players from a team to see new team combinations, and the website will be automatically updated with the newest information. We will also allow for the user to create their own custom player which can be added to any team they choose.

This application will be useful for coaches to better examine how player’s perform and display potential new rosters. This could also help coaches to consider potential player addition or whether they should release a current player. It also will allow for students or anyone interested to access this information. 

No other website shares information about only Florida Division One basketball teams with as much relevant information about each player, nor does any other website allow for the removal and replacement of players to create new potential teams. Some websites such as the official Florida State site have roster information but it’s specific to Florida State University only. Other websites, such as ESPN have data for multiple Florida Division One basketball teams. However, they also contain data for many other teams which can make it difficult for users to find data within the specific niche of Florida Division One basketball teams.

	For the E/R Diagram, we have three entities and one weak entity. The Player Entity will have a primary key of PlayerID, that will remain private to the end user, but is used to keep track of the player in the event of a transfer to a different team or college. PlayerNo will keep track of the player based on the number that relates to their team. TeamID connects the Player and Team entities, and are connected by a many-one relationship. A team can consist of multiple players, however a player can be a part of at most one team. Height, Weight, YearInSchool will be statistics relating to the player. 

The Team Entity will have a primary key of TeamID, that will keep track of every university team in Florida. Each team will have a school it belongs to, a mascot that represents the team, and a Win to Loss Ratio along with an overall ranking. A User can create a UserAccount, which will contain a unique Username along with a Password. Each User account can create a CustomStarter Entity, that will have a unique key of TeamName, and will contain a list of Players, and have a Ranking. Each UserAccount can create multiple CustomStarters but each CustomStarter must be related to one UserAccount. The database is designed to accommodate functional dependencies by ensuring that each table is normalized to the third normal form (3NF). Some of our functional dependencies are as follows: 



contains_player: 

TeamName -> PlayerID

Player_ID -> First_Name, Last_Name, Position, Age, Height, Weight

custom_starter: 

Team_Name, UserName -> Ranking, UserName

UserName -> Team_Name, Ranking

team_ID:

Team_Name -> Team_ID

Player_ID -> Team_ID

useraccounts:

Username -> User_ID, Email, Password

Email -> User_ID, Username, Password

player: 

PlayerID -> PlayerNo, TeamID, Height, Weight, Year_In_School


	The basic functions of our application include allowing the user to remove players from a team and add new ones, filter rosters by player attributes such as position, year and height, search for players via team ID and player number.Users can also search for teams via team name or Id. For example, if a user were to enter “Florida” in the search bar. The results will show all teams in the state that have Florida in their name. Users will also be allowed to edit their username and password. The Admin will have access to player info and will be able to edit player info such as player weight, and year in school.
	
Our Advanced Functionality will be to allow the user to create multiple custom teams based on current active players. Using an algorithm related to the teams performance, we calculate the ranking of each custom team. Our application can also allow the user to view rankings for the current thirteen teams. These teams are ranked by wins and losses.

We will be using MySQL for Relational Database Management System, and using Python with Flask framework with Flask’s MySQLDB package, and Python for the language and software platforms. The data is all sourced from MySQL where we manually input the data from many different teams in order to centralize it all on our site. 

Our project, which is a web-based system for managing college basketball statistics and rankings, began on Wednesday, March 29th, 2023. One of the first challenges we faced was setting up MySQL and creating a shared database for our team to work on. Our team member Patric, who has the most experience in SQL, took on this task and was able to successfully connect us to the database. With this accomplished, we created the tables for our database using the relational schema we had designed earlier.

To make collaboration easier, we also created a GitHub repository to host our project and allow for shared work on the website. On April 5th, we started researching Flask and Python to create a local webpage for our project, which proved to be a challenging task. We wanted to create a website that could accept user queries and allow for navigation between different pages.

On April 10th, we simplified our database design and began creating test web pages and filling in our tables with data. To find the data for this project, we used current 2022-2023 rosters for each school that is listed on ESPNs’ website. 

To transfer the data from ESPN’s website to our database, our teammate Julian manually entered each data element into the database table. One of the biggest challenges we faced was transferring the tables from our SQL database to our locally hosted webpage.

On April 19th, we made significant progress towards website usability. Patric added the ability for users to create an account, which is required to access the website. We also implemented a search function, allowing users to sort through teams and data more easily.

 Additionally, we added advanced functions such as the ability to create custom teams and record games, which accurately displays a college's win-loss record and ratio. With these features in place, our web-based system for managing college basketball statistics and rankings is becoming more robust and user-friendly.

Through this project, we have gained experience in web development, database design, and programming in PHP and SQL. One of the hardest problems we encountered was collaborating in an effective way. This was because the site was hosted locally which made sharing data and writing functions difficult. 

Creating a Github repository for sharing project updates greatly helped us overcome this challenge. In the future, this project can be extended by adding features such as real-time updates such as live scores and in-game player stats, mobile compatibility, video highlights, and user authentication. Overall, this project provided a valuable learning experience and practical application of web development and database design concepts.

Picture above is a sample of what a roster for a specific team looks like on our webpage. Pictured above is our web page listing all the teams currently stored in the database. It also showcases the add player and add team functions that are available only to admin. Also shown is the ability to rank the teams in order by clicking on the “Ranking” title. Also, the ability to view each roster of each team and remove the team from the database. Finally, you can search through the database with the search bar, the results can only be filtered based on school name, wins, mascot, ect. 



References:

Garcia-Molina, H., Ullman, J. D., &amp; Widom, J. (2009). Database systems: The complete book. Pearson Prentice Hall. 

SQL tutorial - learn SQL query language. 1Keydata. (n.d.). Retrieved April 27, 2023, from https://www.1keydata.com/sql/sql.html 

Nixon, R. (n.d.). Robinnixon/LPMJ6: Examples from learning PHP, MySQL &amp; Javascript Ed 6 by Robin Nixon (plus all examples from previous editions). GitHub. Retrieved April 27, 2023, from https://github.com/RobinNixon/lpmj6 

YouTube. (n.d.). Corey Schafer. YouTube. Retrieved April 27, 2023, from https://www.youtube.com/@coreyms/playlists 

Dyouri, A. (2022, December 20). How to make a web application using flask in python 3. DigitalOcean. Retrieved April 27, 2023, from https://www.digitalocean.com/community/tutorials/how-to-make-a-web-application-using-flask-in-python-3

Draw.io - free flowchart maker and diagrams online. Flowchart Maker &amp; Online Diagram Software. (n.d.). Retrieved April 27, 2023, from https://app.diagrams.net/ 

Welcome to flask. Welcome to Flask - Flask Documentation (2.3.x). (n.d.). Retrieved April 27, 2023, from https://flask.palletsprojects.com/en/2.3.x/ 

Men's basketball. Florida State Seminoles. (n.d.). Retrieved April 27, 2023, from https://seminoles.com/sports/basketball/roster/ 

University of Central Florida Athletics. UCF Athletics. (n.d.). Retrieved April 27, 2023, from https://ucfknights.com/sports/mens-basketball/roster 

USF Athletics. (n.d.). Retrieved April 27, 2023, from https://gousfbulls.com/sports/mens-basketball/roster 

Florida Gators Basketball Roster. Florida Gators. (n.d.). Retrieved April 27, 2023, from https://floridagators.com/sports/mens-basketball/roster 

Men's basketball. University of Miami Athletics. (n.d.). Retrieved April 27, 2023, from https://miamihurricanes.com/sports/mbball/roster/ 

Florida International University Athletics. FIU Athletics. (n.d.). Retrieved April 27, 2023, from https://fiusports.com/sports/mens-basketball/roster 

Florida Atlantic University Athletics. (n.d.). Retrieved April 27, 2023, from https://fausports.com/sports/mens-basketball/roster 

Florida A&amp;M University Athletics. Florida A&amp;M. (n.d.). Retrieved April 27, 2023, from https://famuathletics.com/sports/mens-basketball/roster 

The official website of Bethune-Cookman Athletics. Bethune-Cookman University Athletics. (n.d.). Retrieved April 27, 2023, from https://bcuathletics.com/sports/mens-basketball/roster 

Stetson University Athletics. (n.d.). Retrieved April 27, 2023, from https://gohatters.com/sports/mens-basketball/roster 

Jacksonville University Athletics. Jacksonville University. (n.d.). Retrieved April 27, 2023, from https://judolphins.com/sports/mens-basketball/roster 
