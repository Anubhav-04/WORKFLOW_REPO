## CI Continous Integration
Take one example of netflix

developer updated the code on his branch and pushed send pull req

lead dev reviewed and merged

when new code updated to main branch

login to your aws instance --> clone the updated code

--> build the code to install req dependencies

--> test the functionalities

if all good then deploy (publish)

this process we can automate using CI / CD

What is CI
its a software development practice where developers frequently merge their code into shared repos

every time when the new push to main repo it triggers build and test stage aytomatically to ensures new code works well.

Helps us to detect early bugs, improve software quality.

What Tools we can use for
Version Control: GitHub, GitLab, BitBucket
CI Servers: Jenkins, GitHub Actions, GitLab Ci/CD, Travis CI, Circle CI
Build tools: Maven, Gradle, npm, pip
Testing Framework: JUnit, PyTest, Jest, Mocha
Let's Try to Setup a project to see CI workflow
create one repository on github
in local create one folder named project
under that folder create folders .github/workflows
create file named basic-ci.yml
name: Basic CI Pipeline
# Trigger this pipeline on every push
on: [push]

jobs:
    builds:
        runs-on: ubuntu-latest

        steps:
            - name: Say Hello
              run: echo "Hello From CI Pipeline"
push the code to git hub

you can check in your Github Actions the pipeline build or failed

You can expands the build or fails and check the logs

change the pipeline code mentioned below and check output

name: Basic CI Pipeline

# Trigger this pipeline on every push

on: [push]

jobs:
    builds:
        runs-on: ubuntu-latest

        steps:
            - name: Build Stage
              run: echo "Application build successfully"
            - name: Test Stage
              run: echo "Test Cases passed"
            - name: Build deploy
              run: echo "Application deplyed successfully"
create one more file upder the workflows folder
sample.yml
name: 

on:
    push:
        branches: [ main ]

jobs:
    build:
        runs-on: ubuntu-latest
        steps:
            - name: build app
              run: echo "build done"
    test:
        runs-on: ubuntu-latest
        steps:
            - name: test app
              run: echo "test done"
    deploy:
        runs-on: ubuntu-latest
        steps:
            - name: deploy app
              run: echo "deploy done"
              
push and check the output
here build, test, deploy are the names of the job