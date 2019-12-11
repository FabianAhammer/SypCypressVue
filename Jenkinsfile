
pipeline {
    agent any

    tools {
        nodejs 'node'
    }

    environment {
        CHROME_BIN = '/bin/google-chrome'
    }

    stages {
        stage('Dependencies') {
            steps {
                sh 'npm i'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Start test server')
        {
            steps {
                sh 'npm run serve'
            }
        }
        stage('Cypress e2e Tests') {
            steps {
                sh 'npm run test:e2e'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}