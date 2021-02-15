pipeline {
    agent any
    tools{
        Maven 'Maven'
    }
    stages {
        stage('Compile')
        {
             steps {
                    sh 'mvn compile'
                
            }
        }
       
        stage('Package') {
            steps {
                    sh 'mvn package'
                
            }
        }
        stage('Test') { 
            steps {
                sh 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
    }
}
