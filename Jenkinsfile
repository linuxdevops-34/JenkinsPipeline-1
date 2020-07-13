pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building the application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the application'
            echo 'Get the DriverPth: ${ChromeDriverPath}'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying the application'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Driver\\Path'
  }
}