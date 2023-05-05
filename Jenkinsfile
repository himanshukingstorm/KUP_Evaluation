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
          sh "kubectl --kubeconfig=$my_var create deployment finalproject --image=himanshukingstorm/todo-app-py:latest"
          sh "kubectl --kubeconfig=$my_var expose deployment finalproject --type=LoadBalancer --port=8000"
          
              }
      
      }
      
    
    }

  }

}
