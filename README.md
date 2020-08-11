# docker-cicd-nodejs-test
[![Build Status](https://travis-ci.org/christopherlorking/docker-cicd-nodejs-test.svg?branch=master)](https://travis-ci.org/christopherlorking/docker-cicd-nodejs-test)

This is a test/example app that wraps a simple JavaScript Fibonacci-number-at-given-index calculator within:
- Multiple Docker containers
- Multiple databases (PostgreSQL and Redis)
- Travis CI for testing and deployment to AWS
- AWS Elastic Beanstalk for hosting the app
- Separate Dev (local) and Production (AWS) environments

Overly complex, doubtful functionality, more than a mouthful to explain to anyone - perfect for learning.

Credit to Stephen Grider for the architecture, JavaScript and idea from his excellent Udemy course [Docker and Kubernetes: The Complete Guide](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/)



### Making use of free services
Docker, Travis CI, Github free accounts will all work as long as Github repo is set to public.

AWS free tier will work for S3, the EC2 instance created by EB, but not for the Redis database. Costs will be minimal regardless (sub $1 USD a month) unless you leave the envinronment running for an extended period of time.


### Requirements - Production
- Clone this repo to your Github account
- Travis CI
	- Need a free account only
	-  Environmental variables
		- AWS_ACCESS_KEY (IAM user must have full AWS EB permissions)
		- AWS_SECRET_KEY
		- DOCKER_ID
		- DOCKER_PASSWORD
	- .travis.yml
		- Set commented 'deploy' section lines to AWS EB environment
		- EB environment must be set to Docker multi container		
- Docker Hub
	- Need a free account only
- AWS
	- Free tier covers most of the usage, but will be minor costs for Redis (ElastiCache) if leave environment spun up.


### Requirements - Dev Environment
- Uses Dockerfile.dev
- More

### TODO
- [ ] Finish README.md
	- [ ] Include diagrams using Mermaid
	- [ ] Describe Dev/Prod environments
	- [x] List requirements
	- [x] Add Travis CI build badge
- [x] Edit .travis.yml to use $DOCKER_ID