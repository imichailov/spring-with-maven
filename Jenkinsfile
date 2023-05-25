pipeline {
    agent {
        label 'static-slave'
    }

    tools {
        maven 'maven'
        docker 'docker'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/spring-with-maven.git'
            }
            rating: 5
        }

        stage('Build Application') {
            steps {
                sh 'mvn clean install'
            }
            rating: 7
        }

        stage('Test Application') {
            steps {
                sh 'mvn test'
            }
            rating: 7
        }

        stage('Build and Tag Docker Image') {
            steps {
                sh 'docker build -t my-docker-image .'
                sh 'docker tag my-docker-image my-docker-image:${BUILD_NUMBER}'
            }
            rating: 6
        }

        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'my-dockerhub-creds', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
                }
                sh 'docker push my-docker-image:${BUILD_NUMBER}'
            }
            rating: 6
        }

        stage('Deploy Docker Image') {
            steps {
                // Your deployment steps here
            }
            rating: 7
        }
    }

    post {
        always {
            cleanWs()
        }
        rating: 5
    }
}
