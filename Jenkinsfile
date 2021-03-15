pipeline {
    environment{
        imagename="demoapp"
        dockerImage=''
    }
    agent {
          docker {
                image 'maven:3.6.3'
                args '-v /root/.m2:/root/.m2'
          }
        }

    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Build Docker image') {
            steps {
                script{
                    dockerImage=docker.build imagename
//                     dockerPush.run
                }
            }
        }
//         stage('Build Docker image') {
//                     steps {
//                         sh 'docker build -t demoapp'
//                         sh 'docker run demoapp'
//                     }
//                 }
//                 stage('Push Docker image') {
//                     environment {
//                         DOCKER_HUB_LOGIN = credentials('docker-hub')
//                     }
//                     steps {
//                         sh 'docker login --username=$DOCKER_HUB_LOGIN_USR --password=$DOCKER_HUB_LOGIN_PSW'
//                         sh './gradlew dockerPush'
//                     }
//                 }

    }
}