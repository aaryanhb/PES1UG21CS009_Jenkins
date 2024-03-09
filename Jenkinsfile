pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Build PES1UG21CS009-1 project
                sh 'mvn clean install' 

                // Compile hello.cpp file
                sh 'g++ -o hello hello.cpp'
            }
            post {
                always {
                    // Display 'Build stage completed' message
                    echo 'Build stage completed'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Print output of .cpp file using shell script
                    sh './hello'
                }
            }
            post {
                always {
                    // Display 'Test stage completed' message
                    echo 'Test stage completed'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploy'
                }
            }
            post {
                always {
                    // Display 'Deploy stage completed' message
                    echo 'Deploy stage completed'
                }
            }
        }
    }

    post {
        always {
            // Display 'Pipeline completed' message
            echo 'Pipeline completed'
        }
        failure {
            // Display 'Pipeline failed' message
            echo 'Pipeline failed'
        }
    }
}
