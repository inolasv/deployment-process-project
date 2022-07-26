

# Pipeline

### Build
Here is where the application is built. The dependencies for the frontend and backend installed. Then, the frontend is linted in the pipeline script to ensure proper code formatting. Finally, the frontend and api are built so that we can see them.
1. Install node, npm
    - any other frontend dependencies
    - any other api dependencies
2. Lint frontend
3. Build 
    - build frontend
    - build api

### Hold
This step in the pipeline requires user approval in order to continue from the build to the deployment of the application.
- user approve continue

### Deploy
At the step, we know that the build is working. So, first we install the required aws/eb cli tools and then install any other depenencies for the frontend and backend applications. Then, like before, they are both built. Finally, using the elastic beanstalk, the api is deployed to the cloud and now can be accessed from the aws link provided.
1. install
    - eb, aws
2. deploy app
    - install dependencies
    - build frontend and api
    - run deployment to elastic beanstalk