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
			steps {
				script {
					echo 'git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}'
					env.fileName = 'git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}'
					
					}
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


