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
    }
}