# Developer Guide: Accessing and Running the Project

## Step 1: Clone the Git Repository
To get a local copy of the project, open a terminal and run:
```
git clone git@github.com:GriffinG223/LEMPtemp.git
```
Or, if using HTTPS:
```
git clone https://github.com/GriffinG223/LEMPtemp.git
```
Navigate into the project folder:
```
cd LEMPtemp
```

## Step 2: Select Your Branch
List all available branches:
```
git branch -r
```
Checkout your assigned branch:
```
git checkout dev1  # Replace dev1 with your assigned branch
```
Make sure your branch is up to date:
```
git pull origin main
```

## Step 3: Start the Project Using Docker
Ensure Docker is installed and running. Then, build and start the project:
```
docker compose up --build -d
```
This will start the required Nginx, PHP, and MySQL containers.

## Step 4: Find the Port the Project is Running On
Since Docker assigns a random available port, you need to find it:
```
docker ps | grep lemp-nginx
```
You will see an output similar to:
```
CONTAINER ID   IMAGE      PORTS
abc123         nginx      0.0.0.0:8081->80/tcp
```
This means the project is running on port 8081.

## Step 5: Access the Project in the Browser
Open your browser and go to:
```
http://localhost:8081
```
(Replace `8081` with the actual port number you found in Step 4.)

## Step 6: Stopping and Restarting the Project
To stop the project:
```
docker compose down
```
To restart it:
```
docker compose up -d
```

## Step 7: Making and Pushing Changes
After making changes, add and commit your work:
```
git add .
git commit -m "Describe your changes"
```
Push your changes to your branch:
```
git push origin dev1  # Replace with your branch name
```

Now you are set up to work on the project! 
