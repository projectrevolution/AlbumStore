pipeline {
    agent any

    stages {

      stage('Checkout') {
        steps {
           checkout scm
        }

      }
      stage('triggered by SCMTrigger') {
        when {
              expression {

                  triggeredBy 'SCMTrigger'
              }

          }
          steps {
              script {
                  echo 'triggered by SCMTrigger'
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
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
