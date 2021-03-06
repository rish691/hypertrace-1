## Testing Hypertrace deployment using end to end tests

### Setup
- Start Hypertrace using [docker-compose](https://github.com/hypertrace/hypertrace/tree/main/docker) or deploy on kubernetes with helm charts available [here](https://github.com/hypertrace/hypertrace/tree/main/kubernetes).
- Run `ingest-traces.sh` script to ingest pre-defined traces


### Run GraphQL Tests

#### Pre-requisites
- Java 11

#### To run GraphQL tests, 
- go to `graphql-e2e-tests` directory using `cd graphql-e2e-tests`. 
- Now to run tests, run `gradlew run`. This will execute all the GraphQL tests. 


| ![space-1.jpg](https://hypertrace-docs.s3.amazonaws.com/graphql-e2e.png) | 
|:--:| 
| *You should see output like this once all tests are successful* |


### Run UI tests

#### Pre-requisites
- NPM 
- Chrome webdriver

#### To run UI tests, 
- go to `ui-e2e-tests` directory using `cd ui-e2e-tests`. 
- UI tests go to each and every page and browse through available data.
- Now run `npm install` which will install all necessary modules to run tests. 
- To install chrome Driver run the command: `CHROMEDRIVER_RELEASE="$(curl -sS chromedriver.storage.googleapis.com/LATEST_RELEASE)" && npm run install-web-driver -- --versions.chrome=${CHROMEDRIVER_RELEASE}`
- Now to the UI tests, run `npx protractor protractor.conf.js --suite smoke --baseUrl 'http://localhost:2020'`

| ![space-1.jpg](https://hypertrace-docs.s3.amazonaws.com/ui-e2e.png) | 
|:--:| 
| *You should see output like this once all tests are successful* |
