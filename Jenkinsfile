pipeline {
    agent any
    tools {
        maven 'M2_HOME'
        

    }
        stages {
            stage('Hello') {
                steps {
                    echo 'Hello'
                    sleep 5
                }
            }
            stage('Build') {
                steps {
                    sh 'mvn clean'
                    sh 'mvn install'
                    sh 'mvn package'
                }
            }
            stage('Test'){
                steps {
                    sh "mvn test"
                }
            }
        }
}