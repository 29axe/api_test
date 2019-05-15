node {
    
  stage('Build') {
    sh 'cp /home/jenkins/hotmaps/secrets.py ./api/app/secrets.py'
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
