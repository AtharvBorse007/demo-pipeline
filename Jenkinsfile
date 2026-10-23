pipeline {
  agent {
    docker { image 'node:20' }
  }
  stages {
    stage('Build') {
      steps { sh 'node --version' }
    }
  }
}
