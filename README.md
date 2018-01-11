# uva-frank-batten-code-challenge

All rights reserved. Author: Andrey Suntsev 01/11/2018

High fidelity design mockup of the Schools' "Simulation Games" Web page.
This web page has been created to address one of the requirements listed in the 
"Technical Code Challenge" document:

Problem Statement:
The Center for Leadership Simulation and Gaming at the Frank Batten School of Leadership
and Public Policy has various simulation games. These simulation games can be found here.
The challenge is to create a webpage for these simulation games.

Please note:

-   despite on the page is fully functional (i.e. it can be run through web browser and viewed), 
    it is not substitution for the existing "Simulation Games" page;

-   This mockup addresses the only one goal: to serve as a subject of discussion about how new 
    "Simulation Games" page MIGHT BE redesigned. 

-   That is why the page is server less, it's standalone. Other words to be run, it does not 
    require any Web services, database, user authentication and so on. It simply represents 
    some ideas how user interface can be designed.

------------------------------------------------------------------------------------------------
How to access the page's repository through web browser:
------------------------------------------------------------------------------------------------

https://github.com/asuntsev/uva-frank-batten-code-challenge.git

Please notice that this is not way to run the page, instead this URL provides the only access to 
the GitHub file repository where all needed for the project files are stored.

In order to run the page (to verify its interactivity features), you may consider the following options:

1. Copy overall GitHub repository to your Windows or Linux computer and make it searchable for 
   the Apache Web Server (described below);

2. Run it from Andrey Suntsev's AWS EC2 Linux instance by link: 

   http://ec2-54-158-25-204.compute-1.amazonaws.com/uva-gswp/index.html

------------------------------------------------------------------------------------------------
Manually setting up Windows machine:
------------------------------------------------------------------------------------------------

1. Run Apache web server from Windows command line interface:

   > cd c:\Apache24\bin
   > httpd

   If you do not have Apache Web server installed on your Windows machine, please have it installed first following
   to instructions available online.

2. Check if the Apache Web server works properly. Type in your browser the following URL:

   http://localhost/

   If it works as it should, you'll see test Apache web page.

3. Now copy whole directory structure of the "Simulation Games web page mockup" from GitHub repository (see link above)
   to the c:\Apache24\htdocs folder. You should have the following directory structure in the c:\Apache24\htdocs folder:

   c:\Apache24\htdocs\css         -- folder
   
   c:\Apache24\htdocs\fonts       -- folder
   
   c:\Apache24\htdocs\images      -- folder
   
   c:\Apache24\htdocs\js          -- folder
   
   c:\Apache24\htdocs\index.html  -- plain file
   
    
4. Start the page by typing in your browser the following URL:

   http://localhost/index.html#

   The "Simulation Games mockup web page" should be shown and ready to interact with you.

------------------------------------------------------------------------------------------------
Manually setting up Linux machine:
------------------------------------------------------------------------------------------------

1. Run Apache web server from Windows command line interface:

   $ service httpd start

   If you do not have Apache Web server installed on your Linux Server, please have it installed first following
   to instructions available online.

2. Now copy whole directory structure of the "Simulation Games web page mockup" from GitHub repository (see link above)
   to the /var/www/html folder (you should have ROOT privileges). You should have the following directory structure in the c:\Apache24\htdocs folder:

   /var/www/html/css         -- folder
   
   /var/www/html/fonts       -- folder
   
   /var/www/html/images      -- folder
   
   /var/www/html/js          -- folder
   
   /var/www/html/index.html  -- plain file
   
    
3. Set up ownership and permissions for all files from this directory:

   $ cd /var/www
   
   $ find /var/www/html -type d -exec chmod 775 {} +
   
   $ find /var/www/html -type f -exec chmod 664 {} +
   
   $ find /var/www/html -exec chown ec2-user:ec2-user -R {} +
   
4. Start the page by typing in your browser the following URL:

   http://[Your Linux Web Server Host name]/index.html#

   The "Simulation Games mockup web page" should be shown and ready to interact with you.

------------------------------------------------------------------------------------------------
To convert this "Simulation Games web page mockup" into production web site, I would suggest 
to consider the following options:
------------------------------------------------------------------------------------------------

0. Discuss the web page UI to determine set of features to be implemented. It's where the 
   "Simulation Games web page mockup" will be playing its role;

1. Add user (Gamer) authentication. A mechanic of user authentication should follow a policies 
   and technics established in UVA;

2. Add server tier supporting the web site. This tier could consist of two things:

       - Database to store Game's and Gamer's data:

              - initial data sets for constructing the page's content dynamically (list of Games and 
                their descriptions, for instance)
              - Game's status associated with particular Gamer;
              - any other data to support gaming sessions

       - Set of Web Services to make data stored in database available for client application

3. Redesign UI of client web page making it fully responsive. This should keep it usable and 
   good looking in various devices having different size of viewing area.

4. Test the web page in different browsers using a tools available online (SauceLabs, Selenium etc);
  
5. Think about switching from local infrastructure to Cloud computing. This step should be 
   coordinated with other UVA's departments, schools, and plans.

Andrey Suntsev
 

