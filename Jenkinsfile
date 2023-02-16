pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'g++ -o my_program my_program.cpp'
      }
    }

    stage('Test') {
      steps {
        sh './my_program'
      }
    }

    stage('Deploy') {
      steps {
        sh 'rsync -avz my_program user@server:/path/to/destination'
      }
    }
  }

  post {
    always {
      junit 'test-results.xml'
    }
    failure {
      echo 'pipeline failed'
    }
  }
}

