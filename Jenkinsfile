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
		stage ('Parallel') {
			failFast true
			parallel {
				stage('Build 1') { agent any
					steps {
						echo 'this is build 1'
					}
				}
				stage('Build 2') { agent any
					steps {
						echo 'this is build 2'
					}
				}
				stage('Build 3') { agent any
					steps {
						echo 'this is build 3'
					}
				}
				stage('Build 4') { agent any
					steps {
						echo 'this is build 4'
					}
				}
				stage('Build 5') { agent any
					steps {
						echo 'this is build 5'
					}
				}
				stage('Build 6') { agent any
					steps {
						echo 'this is build 6'
					}
				}
				stage('Build 7') { agent any
					steps {
						echo 'this is build 7'
					}
				}
				stage('Build 8') { agent any
					steps {
						echo 'this is build 8'
					}
				}
				stage('Build 9') { agent any
					steps {
						echo 'this is build 9'
					}
				}
				stage('Build 10') { agent any
					steps {
						echo 'this is build 10'
					}
				}
				stage('Build 11') { agent any
					steps {
						echo 'this is build 11'
					}
				}
				stage('Build 12') { agent any
					steps {
						echo 'this is build 12'
					}
				}
				stage('Build 13') { agent any
					steps {
						echo 'this is build 13'
					}
				}
			}
		}
	}
}
