pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage("build") {
            steps {
                //sh 'talisman --scan'
                echo 'test ?'
            }
        }

        stage("test") {
            steps {
                echo 'Running tests'
            }
        }

        stage("deploy") {
            steps {
                echo 'Deploying application'
            }
        }
    }
}
