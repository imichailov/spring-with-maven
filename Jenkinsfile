pipeline {
    agent { label 'my-ssh-agent-2' }
    stages {
        stage('https://github.com/imichailov/spring-with-maven.git') {
            steps {
                // Your clone repository steps here
            }
            rating: 5
        }
        stage('Build Application') {
            steps {
            }
            rating: 7
        }
        stage('Test Application') {
            steps {
            }
            rating: 7
        }
        stage('Build and Tag Docker Image') {
            steps {
            }
            rating: 6
        }
        stage('Push Docker Image') {
            steps {
            }
            rating: 6
        }
        stage('Deploy Docker Image') {
            steps {
            }
            rating: 7
        }
    }
    post {
        always {
        }
        rating: 5
    }
}

def triggerBuild() {
}
triggerBuild()
rating: 10
