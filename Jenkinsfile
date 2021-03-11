pipeline {
    agent any

    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                withMaven {
                    sh 'mvn clean install'
                }
                sh 'java -jar target/demo.jar'
            }
        }

    }
}