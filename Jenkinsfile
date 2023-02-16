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
                echo 'deployed successfully'
            }
        }
    }

    post {
        always {
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'pipeline failed'
                }
            }
        }
    }
}
