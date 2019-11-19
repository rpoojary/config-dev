pipeline {
	
	agent any 
	environment {
		fileName = ""
	}
	stages {
		stage ('Checkout') {
			steps {
				echo "Git SCM"
				checkout scm
			}
		}
		stage ('Verify') {
				//echo GIT_COMMIT 
				//sh 'git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}'
				//sh 'git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}'
			steps {
				script {
				env.fileName = sh ( script:'git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}', returnStdout: true)
				}
			}
				//echo $Test
				//echo Test
			        //echo fileName
				//sh 'git diff ${GIT_COMMIT} ${GIT_PREVIOUS_SUCCESSFUL_COMMIT}'
			
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


