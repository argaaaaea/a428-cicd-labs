node {
    stage('Dependencies') {
        docker {
            image 'node:16-buster-slim' 
            args '-p 3000:3000' 
        }
    }
    stage('Build') {
        try {
            sh "npm install"
            sh "npm i"
            echo "finished build process."
        } catch (exc) {
            echo 'Something failed!'
        }
    }
    stage('Test') {
        try {
            sh './jenkins/scripts/test.sh'
            echo "finished test process."
        } catch (exc) {
            echo 'Something failed!'
        }
    }
}