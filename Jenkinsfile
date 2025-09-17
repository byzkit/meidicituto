pipeline {
  agent any
  tools { nodejs 'nodejs' }
  stages {
    stage('Prepare') {
      steps {
        bat 'if not exist newman mkdir newman'
      }
    }
    stage('Install Newman') {
      steps {
        bat 'npm install -g newman newman-reporter-htmlextra'
      }
    }
    stage('Run Postman Collections') {
      steps {
        bat 'newman run Login_API_Test.postman_collection.json -e GameQA_ENV.postman_environment.json -r cli,htmlextra --reporter-htmlextra-export newman/Login_Report.html --export-environment GameQA_ENV.postman_environment.json'
        bat 'newman run Ranking_API_Test.postman_collection.json -e GameQA_ENV.postman_environment.json -r cli,htmlextra --reporter-htmlextra-export newman/Ranking_Report.html'
        bat 'newman run Item_Grant_API_Test.postman_collection.json -e GameQA_ENV.postman_environment.json -r cli,htmlextra --reporter-htmlextra-export newman/ItemGrant_Report.html'
      }
    }
  }
  post {
    always {
      archiveArtifacts artifacts: 'newman/*.html', fingerprint: true
    }
  }
}