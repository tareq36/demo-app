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
        stage('Build Project') {
            steps {
                sh 'mvn clean package'
                echo 'Build Project Done...'
            }
        }
//         stage('Build Docker image') {
//             steps {
//                 sh 'docker build -t demoapp .'
//                 echo 'Build Docker Done...'
// //                 script{
// //                     dockerImage=docker.build imagename
// // //                     dockerPush.run
// //                 }
//             }
//         }
//         stage('Run Docker image') {
//             steps {
//                 sh 'docker run --name demoapp -d -v $(which docker):/usr/bin/docker -p 8085:8085'
//                 echo 'Run Docker Docker...'
//             }
//         }
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