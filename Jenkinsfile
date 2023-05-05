pipeline {
  agent any
  stages {
    stage('Deploy') {
      when {
        anyOf {
          branch 'production'
        }
      }
      steps{
      withCredentials([file(credentialsId: 'pp', variable: 'my_var')]) {
          sh "kubectl --kubeconfig=$my_var apply -f todo_app_deployment.yml"
//           sh "export SERVICE_URL= 'minikube service todo-app --url'"
//           sh "echo 'Project running on: $SERVICE_URL'"        
//           sh "kubectl --kubeconfig=$my_var expose deployment finalproject --type=LoadBalancer --port=8000"
          
              }
      
      }
      
    
    }

  }

}
