node {
    stage('Build') {
        steps {
            try {
                sh "npm install"
                sh "npm i"
                echo "finished build process."
            } catch (exc) {
                echo 'Something failed.'
            }
        }
    }
    stage('Test') {
        steps {
            try {
                sh './jenkins/scripts/test.sh'
                echo "finished test process."
            } catch (exc) {
                echo 'Something failed.'
            }
        }
    }
}