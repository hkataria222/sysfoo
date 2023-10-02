pipeline {
    agent any
    tools {
        maven 'MVN 6.3.2' 
    }
    stages {
        stage('Build') {
            steps { 
                echo 'Build',
                sh 'mvn compile'
            }
        }
       stage('Test') {
            steps { 
                 echo 'test',
                sh 'mvn clean test'
            }
        }
      stage('package') {
            steps { 
                 echo 'package',
                sh 'mvn package -DskipTests'
            }
        }
    }
}
