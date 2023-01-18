pipeline {
  agent any
  stages {
    stage('test'){
      steps {
        bat 'gradlew test'
        archiveArtifacts 'build/test-results/'
        cucumber reportTitle: 'Raport',
        fileIncludePattern: 'target/report.json',
        trendsLimit: 10
        junit'build/test-results/test/TEST-Matrix.xml'
        
      }
    }
      
       stage('Code Analysis'){
      steps {
        withSonarQubeEnv('sonar'){
        bat 'gradlew sonarqube'
        }
      }
      
      
      stage("Code Quality") {
      steps {
          waitForQualityGate abortPipeline: true
      }
    }
      
      
      
      
      
    }
    
}

}
