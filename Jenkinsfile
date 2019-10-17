pipeline {
    agent any 
    stages {
        stage('Code Checkout') { 
            steps {
                git credentialsId: 'githubid', url: 'https://github.com/itrain-demo/maven-example.git'
            }
        }
        stage('Build') { 
            steps {
              withMaven(jdk: 'jdk', maven: 'mavn') {
               sh 'mvn clean compile'
             }
            }
        }
        stage('Test') { 
            steps {
               withMaven(jdk: 'jdk', maven: 'mavn') {
               sh 'mvn test'
             }  
            }
        }
        stage('Package') { 
            steps {
              withMaven(jdk: 'jdk', maven: 'mavn') {
               sh 'mvn package'
             }  
            }
        }
        stage('Docker Image') { 
            steps {
             sh 'echo docker image is build'   
            }
        }
        stage('Deploy to Dev') { 
            steps {
             sh 'echo Deploy to Dev'   
            }
        }
        stage('Deploy to prod') { 
            steps {
              sh 'echo Deploy to Prod'  
            }
        }
    }
}
