pipeline {
  agent any
  tools {
    maven 'salut'
  }
  stages {
    stage("build") {
      steps {
        sh 'mvn -v' 
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
