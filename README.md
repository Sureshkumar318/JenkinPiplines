Jenkins Pipeline Demo (Node.js + Docker)

This repository contains a simple Jenkins Pipeline that demonstrates:

Running a Jenkins pipeline with a Docker agent

Executing basic shell commands

Installing Node.js dependencies using npm install

📂 Pipeline Overview
Jenkinsfile
pipeline {
    agent {
        docker { image 'node:16-alpine' }
    }

    stages {
        stage('Check Node.js Version') {
            steps {
                sh 'node --version'
            }
        }
        stage('Check Working Directory') {
            steps {
                sh 'pwd'
            }
        }
        stage('List Files') {
            steps {
                sh 'ls -ltr'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
    }
}

🚀 How it works

Jenkins runs the pipeline using the Node.js 16 Alpine Docker image.

It checks the Node.js version inside the container.

Prints the working directory.

Lists all files in the Jenkins workspace.

Runs npm install to install project dependencies (if package.json exists).

🛠️ Prerequisites

Jenkins with Docker support enabled

Node.js project with a package.json file (optional, for npm install step)

▶️ Running the Pipeline

Copy this Jenkinsfile into your repository root.

In Jenkins, create a Pipeline job pointing to this repo.

Run the job — Jenkins will automatically spin up the container and execute the stages.
