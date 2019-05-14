node {
    
  stage('Build') {
    sh 'docker-compose up -f docker-compose-run-api-only.yml --build -d'
  }

  stage('Test') {
    
  }

/*docker.image('geographica/gdal2:latest').inside {
    stage('Test') {
        sh 'python --version'
    }
}*/
}
