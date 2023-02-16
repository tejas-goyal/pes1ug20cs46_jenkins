pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'g++ -o test test.cpp'
      }
    }

    stage('Test') {
      steps {
        sh './test'
      }
    }

    stage('Deploy') {
      steps {
        sh 'rsync -avz test user@server:/path/to/destination'
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

