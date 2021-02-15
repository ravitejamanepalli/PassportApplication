pipeline {
    agent any
    
    stages {
        stage('Clean')
        {
             steps {
                    sh 'mvn clean'
                
            }
        }
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
