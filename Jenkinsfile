pipeline {
  agent any
  stages {
    stage('scm checkout') {
      steps {
        git branch: 'master', url: 'https://github.com/kumargaurav039/maven-project.git'
      }
    }

    stage('package job') //valiadte, compile, test & then package
    {
      steps {
          withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MVN_HOME', mavenSettingsConfig: '', traceability: true) {
          
          withSonarQubeEnv(credentialsId: 'sonarconnection', installationName: 'sonar' ) {
             sh 'mvn package sonar:sonar'}
                }
          
          
          
          }
        }


      }

    

      }


    
