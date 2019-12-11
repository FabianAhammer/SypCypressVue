
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
        stage('Cypress e2e Tests') {
            steps {
                 wrap([$class: 'Xvfb']) 
                 {
                     sh 'npm run test:acceptance'                    
                 }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}