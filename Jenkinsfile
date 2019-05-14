node {
    
  stage('Build') {
    checkout scm
    sh 'docker-compose -f docker-compose-run-api-only.yml up -d --build'
  }

  stage('Test') {
    
  }
}

