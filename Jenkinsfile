pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git branch : 'main',
                url : 'https://github.com/hwafa/timesheetproject.git'
            }
        }
         stage('Compile') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('MVN Sonarqube') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=123 -Dmaven.test.skip=true'
            }
        }
        
    }
}
