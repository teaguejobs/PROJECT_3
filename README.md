# PROJECT_3
MERN STACK IMPLEMENTATION

`STEP 1 – BACKEND CONFIGURATION`

1. Update ubuntu
2. Upgrade ubuntu
3. We get the location of Node.js software from Ubuntu repositories.
4. Install Node.js on the server
5. Verify the node installation with the command (node -v & npm -v)

- `Application Code Setup`
1. Create a new directory for our To-Do project
2. Now change our current directory to the newly created one (Todo)
3.  We use the command "npm init" to initialise our project, so that a new file named "package.json" will be created

- `INSTALL EXPRESSJS`
1. To use express, install it using npm (npm install express)
2. Now create a file index.js with the command (touch index.js)
3. Install the dotenv module
4. Open the index.js file and paste the code  given on documentation
5. Open  terminal in the same directory as your index.js file and type: "node index.js"
6. If every thing goes well, we should see Server running on port 5000 on our terminal.
7. Now we need to open port 5000 in the EC2 Security group we created 
8. Create an inbound rule to open tcp port 5000
9. Open up our browser and try to access your server’s Public IP or Public DNS name followed by port 5000: (http://<PublicIP-or-PublicDNS>:5000)

- `There are three actions that our To-Do application needs to be able to do:`
1. create a new task
2. Display list of all tasks
3. Delet a completed task

Each task will be associated with some particular endpoint and will use different standard HTTP request methods: POST, GET, DELETE

For each task, we need to create routes that will define various endpoints that the To-do app will depend on

1. create a folder route (mkdir routes)
2. Change directory to routes folder
3. Now, create a file api.js 
4. Open the file with the command vim api.js and paste the code given on documentation
- 	`MODELS`

1. Change directory back Todo folder with cd .. and install Mongoose
2. Create a new folder models
3. Change directory into the newly created ‘models’ 
Inside the models folder, create a file and name it todo.js
4. Open the file created with vim todo.js then paste the code given in documentation
5. In Routes directory, open api.js with vim api.js, delete the code inside and paste the code given in the dovumentation

- `MONGODB DATABASE`
