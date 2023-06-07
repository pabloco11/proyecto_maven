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
        stage('SCM') {
            steps {
                checkout scm
            }
        }
        stage('SonarQube Analysis') {
            steps {
                def mvn = tool 'Maven 3'
                withSonarQubeEnv() {
                    sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=EjercicioM3-L4 -Dsonar.projectName='EjercicioM3-L4'"
                }
            }
        }
    }
}
