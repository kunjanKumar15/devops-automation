pipeline {
    agent any
    tools{
       maven 'maven_3_9_6'
   }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kunjanKumar15/devops-automation.git']]])
               sh 'mvn clean install'
                echo "build stage"
            }
        }
       stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t DockerImage-1/devops-integration .'
                    echo "build docker image"
                    echo "sudo docker images"
                }
            } 
            
        }
        stage('Push image to Hub'){
            steps{
                script{
                   //withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'dockerhubpwd')]) {
                   sh 'docker login -u kunjan15 -p Hello@1234'
                   sh 'docker tag DockerImage-1/devops-integration docker.io/kunjan15/dockerimage-1'
                   sh 'docker push kunjan15/dockerimage-1'
                   echo "Docker Image pushed on docker hub successfully"
                   sh 'docker run -d -p 8081:8080 --name MyFirstApplication DockerImage-1/devops-integration'
                     }
                   
                }
            }
      /*  }
        
        stage('docker to k8s'){
            steps{
                script{
                  //sh 'ls /opt/homebrew/bin/ | grep oc'
                  //sh 'cd /opt/homebrew/bin'
                  //sh  'oc login --token=sha256~3upv90iLhBpXlEAJSHortQLddHysDSpcG0XHKImQosE --server=https://api.sec-patch.cp.fyre.ibm.com:6443'
                    kubernetesDeploy (configs: 'deploymentservice.yaml',kubeconfigId: 'k8sconfigpwd')
                }
            }
        }
        */
    }
}