node {
    stage('Build') {
        agent {
            docker {
                image 'node:16-buster-slim' 
                args '-p 3000:3000' 
            }
        }
        steps {
            withNPM(npmrcConfig: 'my-custom-nprc') {
                sh "npm install"
                sh "npm i"
                echo "finished build process."
            }
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