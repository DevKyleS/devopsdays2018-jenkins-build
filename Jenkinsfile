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
	}
}
