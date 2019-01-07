pipeline {
    agent any 
    stages {
        stage('Clone Build') {
            steps {
                sh 'git clone https://github.com/LuckyReddyGIT/Pipeline.git'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn package'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
