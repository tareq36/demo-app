pipeline {
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
                sh 'mvn clean install'
                sh 'java -jar target/demo.jar'
            }
        }

    }
}