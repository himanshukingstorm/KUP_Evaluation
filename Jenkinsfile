pipeline {
    agent any
    stages {
      stage('Build') {
            when {
                anyOf{
//                     branch 'production'
//                     branch 'testing'
                    branch 'master'
                }
            }
            steps {
                sh 'sudo docker build -t todo-app-py .'
                echo "This is Build Based on Docker Image"
                // sh 'mvn package'
            }
        }
//         stage('Deploy to Production') {
//             environment {
//                 TOMCAT_URL = 'http://3.0.176.113:8080'
//                 TOMCAT_USER = 'tomcat'
//                 TOMCAT_PASSWORD = 'tomcat'
        
//             }
//             when {
//                 branch 'production'
//             }
                
//             steps {
            
//                 sh "curl --upload-file /home/ubuntu/Projects/java-war-example-HelloWorld/target*.war ${TOMCAT_URL}/manager/deploy?path=sparkjava-hello-world-1.0 -u ${TOMCAT_USER}:${TOMCAT_PASSWORD}"
//             }
//         }
    }
}
