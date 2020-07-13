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
          environment {
            LocalVariable = 'HelloLocal'
          }
          steps {
            writeFile(file: 'LogTestFile.txt', text: "This is an automation file log ${ChromeDriverPath} and ${LocalVariable} ")
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to Deploy non-master?', id: 'OK')
            echo 'Deploying the application'
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Driver\\Path'
  }
}