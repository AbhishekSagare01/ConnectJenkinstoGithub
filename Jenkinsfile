pipeline {
  agent any
  stages {
    stage('Requirements') {
      parallel {
        stage('Requirements') {
          steps {
            echo 'Installing requirements...'
          }
        }

        stage('parallel to requirements') {
          steps {
            echo 'I am Abhishek'
          }
        }

      }
    }

    stage('Build') {
      steps {
        echo 'Building..'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing..'
      }
    }

    stage('Report') {
      steps {
        echo 'Reporting....'
      }
    }

    stage('Test2') {
      steps {
        echo 'Testing2'
      }
    }

  }
  post {
    always {
      echo 'This step will run after all other steps have finished.  It will always run, even in the status of the build is not SUCCESS'
    }

  }
  options {
    buildDiscarder(logRotator(daysToKeepStr: '10', numToKeepStr: '10'))
    timeout(time: 12, unit: 'HOURS')
    timestamps()
  }
  triggers {
    cron('@midnight')
  }
}