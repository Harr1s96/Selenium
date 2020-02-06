pipeline {
    agent any
    stages {
        stage('--- package and deploy to Nexus ---') {
            steps {
                sh "mvn clean package"
            }
        }
        stage('-- clone test repository --') {
            steps {
                sh "git clone https://github.com/Harr1s96/Selenium.git"
            }
        }
        stage('-- run maven test --') {
            steps {
                    sh 'cd Selenium'
                    sh 'mvn test'
            }
        }
    }
}
