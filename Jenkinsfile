pipeline {
    agent {
        docker {
            image 'node:16-buster-slim' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Build') { 
            step {
                if (env.BRANCH_NAME == 'react-app') {
                    sh "npm install"
                    sh "npm i"
                    echo "finished build process."
                }
            }
        }
        stage('Test') {
            step {
            if (env.BRANCH_NAME == 'react-app') {
                sh './jenkins/scripts/test.sh'
                echo "finished test process."
                }
            }
        }
    }
}