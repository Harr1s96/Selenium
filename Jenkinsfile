pipeline {
    agent any
    stages {
        stage('--- package and deploy to Nexus ---') {
            steps {
                sh "mvn clean package deploy"
            }
        }
        stage('-- build docker image --') {
            steps {
                sh "docker build -t selenium-test ."
            }
        }
        stage('-- deploy image to Docker Hub --') {
            steps {
                withDockerRegistry([credentialsId: "docker-credentials", url: ""]) {
                    sh 'docker tag selenium-test bigheck123/selenium-test'
                    sh 'docker push bigheck123/selenium-test'
                }
            }
        }
    }
}
