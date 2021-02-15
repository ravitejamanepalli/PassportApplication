pipeline {
    agent any 
    stages {
        stage('Git')
        {
            steps{
            git branch: 'master' , url : 'https://github.com/RaviTeja-Manepalli/PassportApplication.git'

            }
        }
        stage('Build') {
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
