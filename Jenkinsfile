pipeline{
    agent {
        node{
            label 'maven'
        }
    }
environment{
    PATH = "/opt/apache-maven-3.9.14/bin:$PATH"
}
    stages{
        stage('Build'){
            steps{
                echo 'Building...'
                sh 'mvn clean deploy'
            }
        }
    }
}