pipeline {
  agent any
  tools {
    maven 'MAVEN_HOME'  // Maven tool name configured in Jenkins
  }
  stages {
    stage('Checkout') {
      steps {
        sh 'echo passed'  // For debugging, to ensure the pipeline is running
        git 'https://github.com/MohanKalyan-K/Docker-Maven-Jenkins.git'
      }
    }
    stage('Build') {
      agent {
        docker { image 'maven:latest' }
      }
      steps {
        script {
          def mvnHome = tool 'MAVEN_HOME'  // Retrieves the Maven installation path
          sh "${mvnHome}/bin/mvn clean package"  // Runs Maven command to clean and package
        }
      }
    }
  }
  post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Please check the logs.'
        }
    }
}
