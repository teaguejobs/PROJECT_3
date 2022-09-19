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
1. Create a MongoDB database and collection inside mLab
2. Create a file in your Todo directory and name it .env.(touch.env), (vi .env)
3. Add the connection string to access the database in it, (DB = 'mongodb+srv://<username>:<password>@<network-address>/<dbname>?retryWrites=true&w=majority')
Ensure you update username,password,database name as given
4.  Now we update the index.js to reflect the use of .env so that Node.js can connect to the database
5. Simply delete existing content in the file (index.js), and update it with the code given in the documentation.
6. Start your server using the command (node index.js) and we will see ,data base connected connected succesfully
7. We will now use postman to test our API 
8. Now open our Postman, create a POST request to the API (http://<PublicIP-or-PublicDNS>:5000/api/todos),This request sends a new task to our To-Do list so the application could store it in the database.
make sure your set header key Content-Type as application/json
9. Create a GET request to your API on http://<PublicIP-or-PublicDNS>:5000/api/todos. This request retrieves all existing records from out To-do application (backend requests these records from the database and sends it us back as a response to GET request).
10. We have successfully created our Backend


`STEP 2 – FRONTEND CREATION`

In the same root directory as your backend code, which is the Todo directory, run:
(npx create-react-app client)
This will create a new folder in your Todo directory called client, where you will add all the react code.

`Running a React App`

1. Install concurrently. It is used to run more than one command simultaneously from the same terminal window.(npm install concurrently --save-dev).
2. Install nodemon. It is used to run and monitor the server. If there is any change in the server code, nodemon will restart it automatically and load the new changes.(npm install nodemon --save-dev).
3. In Todo folder open the package.json file. Change the highlighted part of the below screenshot and replace with the given code in documentation.
("scripts": {
"start": "node index.js",
"start-watch": "nodemon index.js",
"dev": "concurrently \"npm run start-watch\" \"cd client && npm start\""
},)

`Configure Proxy in package.json`

1. Change directory to ‘client’(cd client).
2. Open the package.json file(vi package.json)
3. Add the key value pair in the package.json file "proxy": "http://localhost:5000".
The whole purpose of adding the proxy configuration in number 3 above is to make it possible to access the application directly from the browser by simply calling the server url like http://localhost:5000 rather than always including the entire path like
4. Now, ensure you are inside the Todo directory, and simply do: (npm run dev)
Your app should open and start running on localhost:3000

`Creating your React Components`
1. From your Todo directory run (cd client)
2. Move to the src directory (cd src)
3. Inside your src folder create another folder called components (mkdir components)
4. Move into the components directory with (cd components)
5. Inside ‘components’ directory create three files Input.js, ListTodo.js and Todo.js (touch Input.js ListTodo.js Todo.js)
6. Open Input.js file (vi Input.js).copy and paste the given code in documentation

`To make use of Axios, which is a Promise based HTTP client for the browser and node.js, you need to cd into your client from your terminal and run yarn add axios or npm install axios.`

1. Move to the src folder (cd ..)
2. Move to clients folder (cd ..)
3. Install Axios (npm install axios)
4. Go to ‘components’ directory (cd src/components)
5. After that open your ListTodo.js (vi ListTodo.js)
6. In the ListTodo.js copy and paste the given code in documentation
7. Then in your Todo.js file you write the givn code on documentation

`We need to make little adjustment to our react code. Delete the logo and adjust our App.js to look like this`
1. Move to the src folder (cd ..)
2. Make sure that you are in the src folder and run (vi App.js),then copy and paste the given code in the documentation)
3. In the src directory open the App.css (vi App.css), then paste the given code in the documentation.
4. In the src directory open the index.css (vim index.css)
copy and paste the given code in documentation
5. Go to the Todo directory (cd ../..)
6. When you are in the Todo directory run: (npm run dev)

`Assuming no errors when saving all these files, our To-Do app should be ready and fully functional with the functionality discussed earlier: creating a task, deleting a task and viewing all your tasks.`





