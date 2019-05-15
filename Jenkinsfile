node {
  stage('Init') {
    checkout scm
    sh 'cp /home/jenkins/hotmaps/secrets.py ./api/app/secrets.py'
    sh 'cp -R /home/jenkins/hotmaps/pytest_suit .'
    sh 'cp /home/jenkins/hotmaps/online_status.sh .'
  }
    
  stage('Build') {
    sh 'docker-compose -f docker-compose-run-api-only.yml up -d --build'
    // let some time for the server (API) to start
    sleep 10
    // run script that checks if the API is reachable
    sh './online_status.sh'
  }

  stage('Test') {
    // run API tests
    sh '''
      export WORKSPACE=`pwd`
      virtualenv testenv -p /usr/bin/python
      source testenv/bin/activate
      pip install -U pytest 
      mkdir pytest_reports
      pytest --junitxml=pytest_reports/results.xml /pytest_suit/
    '''
  }
}

