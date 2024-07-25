pipeline {
    agent any
   // tools{
    //    maven 'maven_3_9_6'
    //}
    stages{
        stage('Build Maven'){
            steps{
               // checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kunjanKumar15/devops-automation.git']]])
                //bat 'mvn clean install'
                echo "build stage"
            }
        }
       stage('Build docker image'){
            steps{
                script{
                    //bat 'docker build -t KunjanDockerTest-1/devops-integration .'
                    echo "build docker image"
                }
            } 
            
        }
  /*      stage('Push image to Hub'){
            steps{
                script{
                   //withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'dockerhubpwd')]) {
                   sh 'docker login -u abhikushali -p Welcometoisl@2024'

//}
                   sh 'docker push abhikushali/devops-integration'
                }
            }
        }
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
