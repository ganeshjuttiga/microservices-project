pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                sh "docker build -t ganeshjuttiga/service:v1 ."
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
