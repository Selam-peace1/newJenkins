pipeline {
    agent any
    environment {
        ANYPOINT_CREDENTIALS = credentials('anypointplatform')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'mvn test'
            }
        }
        stage('Deploy to Cloudhub') {
            steps {
                echo 'Deploying to Cloudhub...'
                bat 'mvn mule:deploy -DmuleDeploy -DmuleVersion=4.9.0 -Dusername=Selam-New -Dpassword=Selamet@123 -DworkerType=Micro -Dworkers=1 -Dregion=US-East-2'
            }
        }
    }
}
