pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git branch : 'master ',
                url : 'https://github.com/hwafa/timesheetproject.git'
            }
        }
         stage('Compile') {
            steps {
                sh 'mvn clean compile'
            }
        }
/*
        stage('MVN Sonarqube') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=sonar -Dmaven.test.skip=true'
            }
        }
        */
  stage('MVN Nexus') {
            steps {
                sh 'mvn install -Dmaven.test.skip=true'
            }
        }

stage('build Image ') {
            steps {
                sh 'docker build -t nourbouafoura/timesheet-devops-1.0 . AtelierDevOps/Dockerfile'
             }
         }
    }
}
