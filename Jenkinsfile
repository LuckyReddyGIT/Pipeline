pipeline {
    agent any 
    stages {
        stage('Clone Build') {
            steps {
                sh 'git clone '
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test package'
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
