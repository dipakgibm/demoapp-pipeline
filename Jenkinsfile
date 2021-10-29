pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'Build demo app'
        sh 'sh run_buld_script.sh'
      }
    }

    stage('Linux Tests') {
      parallel {
        stage('Linux Tests') {
          steps {
            echo 'Run Linux tests'
            sh 'sh run_linux_tests.sh'
          }
        }

        stage('window Tests') {
          steps {
            echo 'Window Tests'
          }
        }

      }
    }

    stage('Deply Staage') {
      steps {
        echo 'deploying to staging environment'
        input 'Okay to deployed to production!'
      }
    }

    stage('Deply production') {
      steps {
        echo 'Deploy to production'
      }
    }

  }
}