pipeline {
  agent any
  stages {
    stage('Preparing') {
      steps {
        echo "Preparing..."
      }
    }

    stage('Do stuff') {
      steps {
        echo "Working..."
      }
    }


    stage('WORK') {
      steps {
        build 'work'
      }
    }


    stage('Clean') {
      steps {
        echo "Cleaning..."
      }
    }
  }
  options {
    skipDefaultCheckout()
  }
}