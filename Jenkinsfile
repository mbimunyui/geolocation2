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
                    mvn 'clean'
                    mvn 'install'
                    mvn 'package'
                }
            }
        }
}