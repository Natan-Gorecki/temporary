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
        script{
          def pipelineWORK = load "jenkins/work"
          pipelineWORK.pipeline()
        }
      }
    }


    stage('Clean') {
      steps {
        echo "Cleaning..."
      }
    }
  }
}