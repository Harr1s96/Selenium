pipeline {
    agent any
    stages {
        stage('-- clone test repository --') {
            steps {
                sh "git clone https://github.com/Harr1s96/Selenium.git"
            }
        }
        stage('-- run maven test --') {
            steps {
                    sh 'cd Selenium'
                    sh 'mvn test'
                    sh 'rm -rf /home/jenkins/.jenkins/workspace/selenium-pipeline/Selenium'
            }
        }
    }
}
