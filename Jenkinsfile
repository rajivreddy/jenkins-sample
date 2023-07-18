pipeline {
  agent none
  stages {
    stage('clone') {
      steps {
        echo 'clone'
      }
    }

    stage('Build') {
      steps {
        echo 'build'
      }
    }

    stage('Deploy to Dev') {
      steps {
        echo 'deploy to dev'
      }
    }

    stage('Approve') {
      steps {
        input(message: 'Deploy to QA', id: 'QA', ok: 'yes', submitter: 'yes', submitterParameter: 'yes')
      }
    }

    stage('Deploy to QA') {
      parallel {
        stage('Deploy to QA') {
          steps {
            echo 'deploy to QA'
          }
        }

        stage('test') {
          steps {
            echo 'echo'
          }
        }

      }
    }

    stage('Deploy to UAT') {
      steps {
        echo 'Hello'
      }
    }

  }
}