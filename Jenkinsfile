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
          triggeredBy 'SCMTrigger'


          }
          steps {
              script {
                  echo 'triggered by SCMTrigger'
              }
          }
      }

        stage('Build') {
            steps {
                sh 'npm i'
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
         stage('print our build causes') {
            steps {
                echo "${currentBuild.buildCauses}"
            }
        }
    }
}
