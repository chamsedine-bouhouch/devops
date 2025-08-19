# Jenkins

## Definition

pipeline as a code

## Scripted pipeline: groovy syntax: advanced & flexible

## Declarative:

- "pipeline" : must be top-level
- "agent" : where to execute
- "stages" : where the work happens
- "stage" and "steps"

create a jenkins docker image
docker run -p 8080:8080 -p 50000:50000 -d -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts

## Jenkins project types

- freestyle: simple single tasks
- pipeline: whole delivery cycle
  eg: test| build | ...
- multi branches-pipeline : like pipeline for multiple branches

## Example: Jenkinsfile

```groovy
pipeline {
    agent any
    tools {
        nodejs 'node-24'  // Define a Node.js tool named 'node-24'
    }
    stages {
        stage('checkout') {
            steps {
                echo 'checkout the code'
            }
        }
        stage('install dependencies') {
            steps {
                echo 'install dependencies'
                sh 'npm install'
            }
        }

        stage('test') {
            steps {
                echo 'run tests'
                sh 'npm run test'
            }
        }
        stage('build') {
            steps {
                echo 'build the application'
                sh 'npm run build'
            }
        }
        stage('deploy') {
            steps {
                echo 'deploy the application'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if the pipeline is successful'
        }
        failure {
            echo 'This will run only if the pipeline fails'
        }
        unstable {
            echo 'This will run only if the pipeline is unstable'
        }
        changed {
            echo 'This will run only if the pipeline status has changed'
        }
    }
}

```
