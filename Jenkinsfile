pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "java --version"
            }
        }
        stage('Test') {
            steps {
                sh "java --version"
            }
        }
        stage('Release'){
            steps {
                withCredentials([usernamePassword(credentialsId: '70d5a7a0-c903-4106-a3c1-65339772b047', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]){
                  sh'''
                  docker login -u $USERNAME -p $PASSWORD
                  docker build -t deepadeepa/project-final:${BUILD_NUMBER} .
                  docker push deepadeepa/project-final:${BUILD_NUMBER}
                  ''' 

               
                  
           
                }
            }
        }
    }}