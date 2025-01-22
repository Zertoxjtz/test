pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage("Build & Analyse avec SonarQube") {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn clean package sonar:sonar'
                }
            }
        }
    }
}
