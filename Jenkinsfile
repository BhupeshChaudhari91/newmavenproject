pipeline {
  agent any
  stages {
    stage('scm checkout') {
      steps {
        git 'https://github.com/kumargaurav039/newmavenproject.git'
      }
    }
    stage('package the code') {
      steps {
        withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MVN_HOME', mavenSettingsConfig: '', traceability: true) 
        withSonarQubeEnv(credentialsId: 'sonar-token', installationName: 'sonar'){
        sh 'mvn package sonar:sonar'
      }
    }
    }
    }
  }

