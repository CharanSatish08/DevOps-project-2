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
                echo 'Building..'
                sh 'mvn clean test -Djacoco.skip=true'
            }
        }
        stage('Tests'){
            steps{
                echo 'Testing..'
                sh 'mvn surefire-report:report'
            }
        }
        stage('Sonar Analysis'){
        environment{
            scannerHome = tool 'sonar-scanner';
        }
            steps{
                withSonarQubeEnv('SonarQube-server') { // If you have configured more than one global server connection, you can specify its name
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}
