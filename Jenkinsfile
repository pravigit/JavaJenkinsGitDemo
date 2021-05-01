pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh 'echo "Compile Started"'
      }
    }

    stage('Unit Tests') {
      parallel {
        stage('Unit Tests') {
          steps {
            sh 'echo "Unit Test Started"'
          }
        }

        stage('Integration Tests') {
          steps {
            sh 'echo "Integration Test Completed"'
          }
        }

      }
    }

    stage('Package') {
      steps {
        sh 'echo "Start Package"'
      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            sh 'echo "Deploy Started"'
          }
        }

        stage('Send EMAIL') {
          steps {
            mail(subject: 'Open Blue Ocean Pipeline', body: 'Congratulations !!!! Your Pipeline is Success', to: 'praveen.ula@gmail.com')
          }
        }

      }
    }

  }
}