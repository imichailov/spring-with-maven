pipeline {

    agent {
        label 'my-ssh-agent-2'
    }

    tools {
        nodejs 'nodejs'
        dockerTool 'docker'
    }

    triggers {
        githubPush()
    }

    environment {
    DOCKERHUB_CREDENTIALS = credentials('my_dockerhub_creds')
    IMAGE_NAME = 'ivanmihaylov/mynodejsapp'
}

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
