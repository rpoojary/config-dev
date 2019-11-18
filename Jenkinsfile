pipeline {
	agent any 
	stages {
		stage ('Verify') {
			steps { 
				echo "Verifying the json"
				git status 
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
