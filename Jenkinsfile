pipeline {
  agent any
  tools {
    maven 'MAVEN HOME' 
  }
  stages {
    stage ('Build') {
      steps {
        bat 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: '9425b3c4-fb6f-4d66-a392-a157fb00e58c', path: '', url: 'http://localhost:8087/')], contextPath: '/pipeline', onFailure: false, war: '**/*.war' 
        }
      }
    }
  }
}
