node {
    
  stage('Build') {
    checkout scm
    sh 'cp /home/jenkins/hotmaps/secrets.py ./api/app/secrets.py'
    sh 'docker-compose -f docker-compose-run-api-only.yml up -d --build'
  }

  stage('Test') {
    
  }
}

