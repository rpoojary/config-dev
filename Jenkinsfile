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
				//echo GIT_COMMIT 
				sh 'git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}'
				//echo fileName
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
