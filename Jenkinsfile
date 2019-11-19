pipeline {
	
	agent any 
	environment {
		fileName = "Rohan"
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
					sh 'git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}'
					env.fileName = sh 'git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}'
					echo "${env.fileName}"
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


