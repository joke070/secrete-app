pipeline {
  agent any

  environment {
    NVM_DIR = '/var/lib/jenkins/.nvm'
    PATH = "${NVM_DIR}/versions/node/v16.20.2/bin:${env.PATH}"
  }

  stages {
    stage('Install') {
      steps {
        sh '''
          source $NVM_DIR/nvm.sh
          nvm use 16
          npm install
        '''
      }
    }

    stage('Test') {
      steps {
        sh '''
          source $NVM_DIR/nvm.sh
          nvm use 16
          npm test
        '''
      }
    }

    stage('Build') {
      steps {
        sh '''
          source $NVM_DIR/nvm.sh
          nvm use 16
          npm run build
        '''
      }
    }

    stage('Deploy') {
      steps {
        sh '''
          scp -i your-key.pem -r ./build ec2-user@your-ec2-ip:/var/www/html/
        '''
      }
    }
  }
}
