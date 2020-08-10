# docker-cicd-nodejs-test
[![Build Status](https://travis-ci.org/christopherlorking/docker-ci-nodejs-test.svg?branch=master)](https://travis-ci.org/christopherlorking/docker-ci-nodejs-test)

This is a test app that wraps a simple JavaScript Fibonacci-number-at-given-index calculator within:
- Multiple Docker containers
- Multiple databases (PostgreSQL and Redis)
- TravisCI for testing and deployment to AWS
- AWS Elastic Beanstalk for hosting the app
- Differing Dev and Production environments

Overly complex doubtful functionality; perfect for learning.
Docker, Travis CI, Github free accounts will all work as long as repo is set to public.
AWS free tier will work for S3, the EC2 instance created by EB, but not for the Redis database. Costs will be minimal regardless (sub $1 USD a month) unless you 


### Requirements - Production
- Travis CI
	- Clone this repo to your Github profile account, Environmental variables
		- AWS_ACCESS_KEY (IAM user must have full AWS EB permissions)
		- AWS_SECRET_KEY
		- DOCKER_ID
		- DOCKER_PASSWORD
	- .travis.yml
		- Set commented 'deploy' section lines to AWS EB environment
		- EB environment must be set to Docker multi container		
- Docker Hub - need a free account


### Requirements - Dev Environment
- Uses Dockerfile.dev
- More

### TODO
- [ ] Finish README.md
	- [ ] Include diagrams using Mermaid
	- [ ] Describe Dev/Prod environments
	- [ ] List requirements
	- [x] Add Travis CI build badge
- [ ] Edit .travis.yml to use DOCKER_ID