pipeline{

    agent any

    stages{

        stage("CONTINOUS DOWNLOAD"){
            steps{
                git branch: 'main', url: 'https://github.com/djimar05/DRA-CI-CD-SIELI.git'
            }
        }

        stage("Unit Test"){
            steps{
                sh 'mvn test'
            }
        }

        stage("Integration Test"){
            steps{
                sh 'mvn verify -DskipUnitTests'
            }
        }

        stage("Continous Build"){
            steps{
                sh 'mvn clean install'
            }
        }

        stage("Static Test Analysis"){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'dra-sonar-token'){
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }

        }
    }
}