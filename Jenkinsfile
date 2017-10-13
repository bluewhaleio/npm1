pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        parallel(
          "checkout": {
            echo 'checkout'
            
          },
          "email": {
            echo 'email'
            
          }
        )
      }
    }
    stage('build') {
      steps {
        echo 'build'
      }
    }
    stage('qa') {
      steps {
        echo 'qa'
      }
    }
    stage('preprod') {
      steps {
        parallel(
          "preprod": {
            echo 'preprod'
            
          },
          "alpha": {
            echo 'alpha'
            
          }
        )
      }
    }
    stage('prod') {
      steps {
        echo 'prod'
      }
    }
    stage('deploy') {
      steps {
        sh './deploy.sh'
      }
    }
  }
}