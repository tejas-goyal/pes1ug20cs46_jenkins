pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o t5 t5.cpp'
            }
        }

        stage('Test') {
            steps {
                sh './t5'
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
