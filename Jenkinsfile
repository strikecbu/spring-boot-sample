pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
      }
    }
    stage('package') {
      steps {
        sh '''make build-docker-prod-image
docker push localhost:5000/java_sample_prod'''
      }
    }
    stage('deploy') {
      steps {
        sh 'make deploy-production-ssh'
      }
    }
  }
  post {
    always {
      echo 'I will always say Hello again!'

    }

    success {
      echo 'success!'

    }

    failure {
      echo 'failure!'

    }

  }
}