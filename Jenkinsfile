pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh 'echo "hello"'
      }
    }

    stage('Deploy') {
      when {
        beforeAgent true
        branch 'master'
      }
      options {
        timeout(time: 30, unit: 'SECONDS')
      }
      input {
        message 'Should we continue?'
      }
      steps {
        echo 'Continuing with deployment'
        input(message: 'Ok?', submitter: 'sre')
      }
    }

  }
}