pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Stage - build'
        isUnix()
        timestamps()
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Step 1'
            echo 'Step 2'
            echo 'Step 3'
          }
        }
        stage('Test-Fork-HZ') {
          steps {
            echo 'Step 1'
          }
        }
      }
    }
    stage('Deploy') {
      agent any
      environment {
        Prod = 'Prod'
      }
      steps {
        echo 'Deploy message'
        pwd()
      }
    }
  }
  environment {
    test1 = 'test1'
  }
}