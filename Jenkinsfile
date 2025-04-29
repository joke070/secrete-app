pipeline {
  agent any
tools {nodejs "nodejs"}
 

  stages {
    stage('Install Dependencies') {
      steps {
        sh 'npn install'
      }
    }

    stage('Test') {
      steps {
        sh 'echo "testing application...."'
      }
    }

    stage("Deploy application") {
      steps {
        sh 'echo "deploying application..."'
      }
    }
  }
}
