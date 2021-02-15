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
                dir ('C:/Windows/System32/config/systemprofile/AppData/Local/Jenkins/.jenkins/workspace/pipeline3'){
                    sh 'mvn package'
                }
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
