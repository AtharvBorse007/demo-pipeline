pipeline {
  agent {
    docker { image 'node:20' }
  }
  stages {
    stage('Build') {
      steps { sh 'node --version' }
    }
  }
    stage('Build') {
  agent {
    docker {
      image 'node:20'
      args '-v /tmp:/tmp'
    }
  }
  steps {
    sh 'npm ci'
    sh 'npm test'
  }
}

}
