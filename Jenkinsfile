pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build'
        sh 'mvn compile'
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'test'
            sh 'mvn clean test'
          }
        }

        stage('') {
          steps {
            echo 'parallel stage'
          }
        }

      }
    }

    stage('package') {
      steps {
        echo 'package'
        sh 'mvn package -DskipTests'
        archiveArtifacts(artifacts: '**/target/*.war', onlyIfSuccessful: true)
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
}