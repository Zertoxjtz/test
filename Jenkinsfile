pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    environment {
        SONARQUBE_SERVER = 'SonarQube'
    }

    stages {
        stage("Build and Analyze") {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn clean install sonar:sonar -Dsonar.projectKey=my-project-key'
                }
            }
        }

        stage("Quality Gate") {
            steps {
                script {
                    timeout(time: 1, unit: 'MINUTES') {
                        def qg = waitForQualityGate()
                        if (qg.status != 'OK') {
                            error "Pipeline failed due to Quality Gate: ${qg.status}"
                        }
                    }
                }
            }
        }
    }
}
