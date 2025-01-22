pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage("build") {
            steps {
                echo 'Building application...'
            }
        }

        stage("test") {
            steps {
                echo 'Running tests...'
            }
        }

        stage("SonarQube Analysis") {
            steps {
                withSonarQubeEnv('Sonarqube') { // Utilise le nom configuré
                    sh 'mvn clean package sonar:sonar'
                }
            }
        }

        stage("deploy") {
            steps {
                echo 'Deploying application...'
            }
        }
    }
}
