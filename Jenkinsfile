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
				env.fileName = sh ( script:'git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}', returnStdout: true)
				}
			      }
			echo "${env.fileName}"
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


