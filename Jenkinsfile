pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Stage - build'
        isUnix()
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Step 1'
            echo 'Step 2'
            echo 'Step 3'
            emailext ( 
              subject: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'", 
              body: """<p>STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
                       <p>Check console output at "<a href="${env.BUILD_URL}">${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>"</p>""",
              to: 'supro200@gmail.com','alexander.zyuzin@vodafone.com'
     )
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
