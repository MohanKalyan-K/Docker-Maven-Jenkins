pipeline {
  agent {
    label 'slave'  // Specifies that this pipeline runs on the node with label 'slave'
  }
  tools {
    maven 'apache-maven-3.9.9'  // Maven tool name configured in Jenkins
  }
  stages {
    stage('Checkout') {
      steps {
        sh 'echo passed'  // For debugging, to ensure the pipeline is running
        git branch: 'main', url: 'https://github.com/MohanKalyan-K/Docker-Maven-Jenkins.git', credentialsId: 'git'
      }
    }
    stage('Build') {
      steps {
        script {
          def mvnHome = tool 'apache-maven-3.9.9'  // Retrieves the Maven installation path
          sh "${mvnHome}/bin/mvn clean package"  // Runs Maven command to clean and package
        }
      }
    }
  }
}
