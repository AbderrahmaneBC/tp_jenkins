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
        
      }
    }
    
}

}
