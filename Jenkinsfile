pipeline {
    agent any 
    environment{
        PATH : "/Windows/System32/config/systemprofile/AppData/Local/Jenkins/.jenkins/jenkins-jobs:$PATH"
    }
   
    stages {
        stage('Git')
        {
            steps{
            git url : 'https://github.com/RaviTeja-Manepalli/PassportApplication.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') { 
            steps {
                bat 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
    }
}
