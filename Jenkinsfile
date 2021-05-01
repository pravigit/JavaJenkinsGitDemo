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
      steps {
        sh 'echo "Deploy Started"'
        emailext(subject: 'Ocen Blue Pipeline Job', body: 'Congratulation !!! Your Ocen Blue Pipeline is SUCCESS', from: 'JenkinsOcenBluePipeline', to: 'praveen.ula@gmail.com')
      }
    }

  }
}