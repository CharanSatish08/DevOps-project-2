pipeline{
    agent any
     tools {
        maven 'MAVEN3.9'
        jdk 'JDK21'
    }
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/CharanSatish08/DevOps-project-2.git'
            }
        }
        stage('Build'){
            steps{
                echo 'Building...'
                sh 'mvn install'
            }
        }
    }
}