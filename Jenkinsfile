pipeline {
	agent any 
	stages {
		stage ('Checkout') {
			steps {
				echo "Git SCM"
				checkout scm
			}
		}
		stage ('Verify') {
			steps { 
				python --help 
				//sh 'git diff ${GIT_COMMIT} ${GIT_PREVIOUS_SUCCESSFUL_COMMIT}'
				}
			}
		stage ('Package') {
			steps {
				echo "Packaging the Config"
				}
			}
		stage ('Upload') {
			steps {
				echo "Uploading Package "
				}
		}
	}
}
