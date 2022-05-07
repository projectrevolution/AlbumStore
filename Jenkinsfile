pipeline {
    agent any
    def packageJson

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
      stage('Setup build environment'){
        steps {

          packageJson = readJSON file: 'package.json'
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
