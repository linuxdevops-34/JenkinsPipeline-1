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
            echo "Get the DriverPth: ${ChromeDriverPath}"
          }
        }

        stage('TestLog') {
          steps {
            writeFile(file: 'LogTestFile.txt', text: 'This is an automation file log')
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to Deploy?', id: 'OK')
        echo 'Deploying the application'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Driver\\Path'
  }
}