pipeline {
    agent any

    stages {
        stage('Build') {
            steps {  // <-- REQUIRED wrapper for all stage actions
                dir('src') {  // Now properly nested in steps
                    sh 'docker build -t ganeshjuttiga/service:v1 .'
                }
            }
        }
        
        stage('push'){
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                            sh "docker push ganeshjuttiga/service:v1"
                     }
                }
            }
        }
    }
}
