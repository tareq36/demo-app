pipeline {
    agent any
    tools {
        maven '3.6.3'
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