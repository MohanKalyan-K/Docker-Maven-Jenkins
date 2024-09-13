pipeline {
  agent {
    label 'slave' //
  }
  tools {
    maven 'apache-maven-3.8.8'
  }
  environment {
    MAVEN_HOME = "/opt/apache-maven-3.8.8"
  }
  stages {
    stage (checkout) {
      steps {
        git branch: 'main', url: 'https://github.com/MohanKalyan-K/Docker-Maven-Jenkins.git'
      }
    }
    stage (Build) {
      script {
        def mvnHome = tool 'apache-maven-3.8.8'
        sh '${mvnHome}/bin/mvn clean package'
      }
    }
  }
{
