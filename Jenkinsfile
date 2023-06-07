pipeline {
    agent any

    stages {
        stage('Clean') {
            steps {
                echo 'Clean'
                sh 'mvn clean install'
            }
        }
        stage('Build') {
            steps {
                echo 'Build'
                sh 'mvn package'
            }
        }
    }
}
