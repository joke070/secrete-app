pipeline {
  agent any

  stages {
    

    stage('Install') {
      steps {
        sh 'npm install' // or pip install -r requirements.txt for Python
      }
    }

    stage('Test') {
      steps {
        sh 'npm test' // adjust this to your app's test command
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build' // or whatever build command your app uses
      }
    }

    stage('Deploy') {
      steps {
        // simple deployment script, e.g., scp or rsync to a server
        sh 'scp -i your-key.pem -r ./build ec2-user@your-ec2-ip:/var/www/html/'
      }
    }
  }
}
