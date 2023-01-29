pipeline {
    agent any
    tools{
        maven 'M2_HOME'
    }
    environment {
    registry = '704819634910.dkr.ecr.us-east-1.amazonaws.com/devop_repository'
    registryCredential = 'jenkins-ecr'
    docker_Image = ''
  }
    stages {
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/mbimunyui/helloworld_jan_22.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
                
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Build Image') {
            steps {
                script{
                    docker_Image = docker.build registry + ":$BUILD_NUMBER"  
                }
            }
        }
        stage('Deploy Image') {
            steps {
                script{
                docker.withRegistry("https://"+registry,"ecr:us-east-1:"+registryCredential) {
                        docker_Image.push()
                }
                }
            }
        }
    }
}
//End of build of project
