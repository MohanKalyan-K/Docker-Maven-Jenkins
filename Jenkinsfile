pipeline {
  agent {
    label 'slave' //
  }
  tools {
    maven 'MAVEN_HOME'
  }
  stages {
    stage ('checkout') {
      steps {
        // git branch: 'main', url: 'https://github.com/MohanKalyan-K/Docker-Maven-Jenkins.git'
      }
    }
    stage ('Build') {
      steps{
        script {
          def mvnHome = tool 'apache-maven-3.8.8'
          sh '${mvnHome}/bin/mvn clean package'
        }
      }
    }
  }
}
