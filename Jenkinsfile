pipeline {
  agent any
  stages {
    stage('Build') {
      when {
        anyOf {
          branch 'master'
        }
      }
      steps {
        sh 'docker build -t todo-app-py:V.$BUILD_NUMBER .'
        echo "This is Build Based on Docker Image version $BUILD_NUMBER"
        // sh 'mvn package'
      }
    }
    stage('Login Dockerhub') {
      steps {
        withCredentials([string(credentialsId: 'kingstorm_dh', variable: 'DOCKER_TOKEN')]) {
          sh "docker login -u himanshukingstorm -p $DOCKER_TOKEN"
        }
        echo "Logged In Successfully"
      }
    }
    stage('Push into Dockerhub') {
      steps {
        sh "docker tag todo-app-py:V.$BUILD_NUMBER himanshukingstorm/todo-app-py:V.$BUILD_NUMBER"
        sh "docker push himanshukingstorm/todo-app-py:V.$BUILD_NUMBER"
      
      echo "This is Push Based on Docker Image as Version :V.$BUILD_NUMBER"
      }
      }
  }

}
