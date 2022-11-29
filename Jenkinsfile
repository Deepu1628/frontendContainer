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
                withCredentials([usernamePassword(credentialsId: 'dockerhubcredentails', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]){
                  sh'''
                  docker login -u $USERNAME -p $PASSWORD
                  docker build -t deepadeepa/project-final:${BUILD_NUMBER} .
                  docker push deepadeepa/project-final:${BUILD_NUMBER}
                  ''' 

               
                  
           
                }
            }
        }
    }}