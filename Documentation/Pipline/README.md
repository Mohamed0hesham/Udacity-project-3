# Steps of the pipline

- I used CircleCi for configuring the pipeline process of this application
- As shown in the `config.yml` in the folder it is the steps of integrating and deploying the app which starts by pushing the code to the git repo that is connected to the CircleCi account and after pushing it automatically triggers the CircleCi which starts working according to the `config.yml` inside the `.circleci` folder wich contains the jobs needed to integrate and deploy the app.
- this approach allows both the CI and CD as follows:

## CI (continuous integration)

- When pushing the code to the git repo, the CircleCi starts the jobs which are:

1. installing the dependencies of the frontend and backend by the command `npm run frontend:install` and `npm run api:install` which are in the package.json in the root folder of the app which initiates the scripts inside each project's `package.json` file.

2. building both the frontend and backend by the command `npm run frontend:build` and `npm run api:build`

3. running tests by the command `npm run frontend:test` and `npm run frontend:e2e`

## CD (continuous delviry)

4. deploying both the backend and the frontend

-backend is deployed with the command `npm run api:deploy` to the AWS Elastic beanstalk
-frontend is deployed with the command `npm run frontend:deploy` to the AWS S3 bucket

-[This is the link to the udagram frontend hosted on the S3 bucket](http://hbucketh.s3-website-us-east-1.amazonaws.com/home)

- I also Designed a simple `pipeline diagram` showing the pipline process in this folder

- I also provided the `config.yml` that contains the pipeline configuration
