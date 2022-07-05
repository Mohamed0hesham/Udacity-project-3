# This "App Structure" folder contains the AWS services that is used for hosting the app

- The application consists of a frontend, backend and database and for that i used aws services for deploying each of them as follows:

1. EB (Elastic beanstalk)

   - I used EB service for hosting the app backend API and its Environment variables by adding a deployment script inside the API package.json that installs using `npm run install`, builds,zips using `npm run build`, and deploys the zip folder to the aws eb using `npm run deploy` command and by the help of the .elasticbeanstalk config.yml file and i also uploaded the required environment variables to the eb using `eb setenv` command to get the values from the environment variables stored on CircleCi.

2. RDS

   - I used RDS service for storing the database of the app using PostgresSQL DB which and added its url to the environment variables so that the eb can use it to connect and send queries and recives responses.

3. S3 bucket

   - I used S3 bucket for hosting the frontend of the app by adding deployment script inside the frontend package.json file that installs using `npm run install`, builds using `npm run build` to the target folder called `www` and then tests the by using `npm run test`,`npm run e2e` and then deploying the content of the `www` folder using `npm run deploy` with the help of the `bin/deploy.sh` file which contains the command.

## Each service's screenshots are inside it's folder here in the Infrastructure folder

## Architecture diagram

- I designed this diagram to show the over all process of this application and how the services are communicating.
