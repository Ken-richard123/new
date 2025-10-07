pipeline {
    agent any

    stages {

        stage('Pull Code From GitHub') {
            steps {
                git 'https://github.com/Ken-richard123/new.git'
            }
        }

        stage('Build the Docker Image') {
            steps {
                sh '''
                    docker build -t weekendimage .
                    docker tag weekendimage kendanel/weekendimage:latest
                    docker tag weekendimage kendanel/weekendimage:${BUILD_NUMBER}
                '''
            }
        }

        stage('Login to DockerHub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: '5fc73a64-3611-4a87-8c61-0f8171552fc4',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                }
            }
        }

        stage('Push the Docker Image') {
            steps {
                sh '''
                    docker push kendanel/weekendimage:latest
                    docker push kendanel/weekendimage:${BUILD_NUMBER}
                '''
            }
        }
        }
}
pipeline {
    agent any

    stages {

        stage('Pull Code From GitHub') {
            steps {
                git 'https://github.com/Ken-richard123/new.git'
            }
        }

        stage('Build the Docker Image') {
            steps {
                sh '''
                    docker build -t weekendimage .
                    docker tag weekendimage kendanel/weekendimage:latest
                    docker tag weekendimage kendanel/weekendimage:${BUILD_NUMBER}
                '''
            }
        }

        stage('Login to DockerHub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: '5fc73a64-3611-4a87-8c61-0f8171552fc4',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                }
            }
        }

        stage('Push the Docker Image') {
            steps {
                sh '''
                    docker push kendanel/weekendimage:latest
                    docker push kendanel/weekendimage:${BUILD_NUMBER}
                '''
            }
        }
        }
}

