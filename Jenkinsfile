pipeline {
    agent any
    tools {
        maven 'Maven 3.8.7'
        jdk 'jdk11'

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
                    mvn 'clean'
                    mvn 'install'
                    mvn 'package'
                }
            }
        }
}