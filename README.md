Lab -  Setting Up and Deploying an Angular Calculator Application on Ubuntu
Objective:
The objective of this lab is to teach students how to set up and deploy an Angular-based web application (Angular Calculator) on a local Ubuntu server. The steps will include cloning the repository, setting up the necessary environment, installing dependencies, building the Angular project, and deploying it using Nginx.

Materials Needed:
Ubuntu system (or any Linux-based operating system)


Node.js and npm installed


Angular CLI installed


Git for cloning the repository


Nginx for serving the Angular application



Prerequisites:
Basic understanding of Angular and web development concepts.


Familiarity with using terminal commands in Linux.


Familiarity with Angular CLI, npm, and Node.js.



Procedure:
1. Setting up the Environment:
Step 1.1: Check the current system hostname
 Open the terminal and run the following command to check the current system hostname:

 hostnamectl


If needed, set the hostname to angular-app by running:


sudo hostnamectl set-hostname angular-app


Step 1.2: Update the system
 Ensure the system packages are up to date:

 sudo apt -y update



2. Clone the Angular Calculator Repository:
Step 2.1: Clone the repository from GitHub
 Navigate to your desired directory and run the following command to clone the Angular Calculator repository:

 git clone https://github.com/Ai-TechNov/AngularCalculator.git


Step 2.2: Navigate into the cloned directory
 Once the repository is cloned, navigate into the project folder:

 cd AngularCalculator



3. Install Dependencies:
Step 3.1: Verify Node.js and npm versions
 Ensure you have Node.js and npm installed:

 node -v
npm -v
 If these are not installed or if the version is outdated, follow the next steps to install the correct versions.


Step 3.2: Install Node.js and npm (if necessary)
 Install Node.js (version 20.x) and npm by running:

 sudo apt-get install -y nodejs
sudo apt install npm -y


Step 3.3: Install project dependencies
 Run npm install to install the dependencies specified in the package.json file:

 npm install



4. Build the Angular Application:
Step 4.1: Build the Angular project
 Run the following command to build the Angular project:

 sudo ng build --prod
 This will generate the production-ready files in the dist/ folder.



5. Install and Configure Nginx to Serve the Application:
Step 5.1: Install Nginx
 If Nginx is not installed, run the following command to install it:

 sudo apt -y install nginx


Step 5.2: Verify Nginx installation
 After installing, check the status of the Nginx service to ensure it is running:

 sudo systemctl status nginx


Step 5.3: Remove the default web content
 Remove any default files present in /var/www/html/:

 sudo rm -rf /var/www/html/*


Step 5.4: Copy the build files to the Nginx root
 After building the application, copy the content of the dist/angularCalc/ folder into Nginx's default root directory:

 sudo cp -r dist/angularCalc/* /var/www/html/


Step 5.5: Restart Nginx
 Restart Nginx to apply the changes:

 sudo systemctl restart nginx



6. Test the Application:
Step 6.1: Access the application via a browser
 Open your browser and navigate to the following URL to see your Angular Calculator app in action:

 http://<your-server-ip>
 If you set this up on a local server, use http://localhost or http://127.0.0.1.



Conclusion:
By following the steps above, students will learn how to:
Clone an Angular project from GitHub.


Install necessary dependencies using npm.


Build the Angular project for production.


Set up and configure Nginx to serve the built Angular files.


Test the application through a web browser.


This hands-on lab covers basic Angular setup and deployment on a Linux-based server, giving students practical skills in both development and deployment pipelines.

Troubleshooting Tips:
If ng build fails, ensure that all dependencies are correctly installed by running npm install.


If Nginx is not starting, verify the configuration files in /etc/nginx/ or check the logs in /var/log/nginx/ for specific errors.


If the app does not display correctly in the browser, check the permissions of the /var/www/html/ directory and ensure that the correct files were copied.



Additional Tasks (Optional):
Modify the Angular Calculator: Students can try modifying the Angular Calculator by adding more features like basic math functions, decimal support, or even a history panel.


Use Git for version control: Encourage students to regularly commit their changes and push them to GitHub.



References:
Angular Official Documentation


Nginx Official Documentation


Node.js Official Documentation



