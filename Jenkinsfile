pipeline {
    agent any
    stages {
      stage('Build') {
            when {
                anyOf{
                    branch 'master'
                }
            }
            steps {
                sh 'docker build -t todo-app-py .'
                echo "This is Build Based on Docker Image"
                // sh 'mvn package'
            }
        }
        stage('Push Image') {
               steps {
                withCredentials([string(credentialsId: 'kingstorm_dh', variable: 'DOCKER_TOKEN')]) {
                   sh "docker login -u "himanshukingstorm" -p $DOCKER_TOKEN"
}

                echo "This is Push Based on Docker Image"
            }
        }
        }
    }
