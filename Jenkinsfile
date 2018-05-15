pipeline {
	agent none
  environment {
    NODE_VER = '8.1.0'
  }
	stages {
		stage('Beginning') { agent any
			environment {
				DEPLOY_VERSION = 'Howdy'
			}
			steps {
				echo 'Hello world'
				sh 'echo $NODE_VER'
				echo "ENVIRONMENT: ${env.DEPLOY_VERSION}"
			}
		}
    stage('Who Am I?') { agent any
			environment {
				DEPLOY_VERSION = 'prod'
			}
      steps {
				echo "ENVIRONMENT: ${env.DEPLOY_VERSION}"
        sh 'whoami'
        sh 'host -t TXT pgp.michaelholley.us | awk -F \'"\' \'{print $2}\''
      }
    }
		stage('Deploy to stage?') { agent none
			steps	{
				input 'Deploy to stage?'
			}
		}
		stage ('Parallel') { agent any
			failFast true
			Parallel{
				stage('Build 1') {
					steps {
						echo 'this is build 1'
					}
				}
				stage('Build 2') {
					steps {
						echo 'this is build 2'
					}
				}
				stage('Build 3') {
					steps {
						echo 'this is build 3'
					}
				}
			}
		}
	}
}
