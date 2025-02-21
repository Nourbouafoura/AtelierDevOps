pipeline {
    agent any
//test conflit
    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Nourbouafoura/AtelierDevOps.git'
            }
        }
        
        stage('Compile') {
            steps {
                sh 'mvn clean compile'
            }
        }
    stage('MVN SONARQUBE') {
        steps 
        {sh 'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=123 -Dmaven.skiptest =true';
    }
}
}
