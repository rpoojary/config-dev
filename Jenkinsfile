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
				sh '''
				#!/bin/sh
				 MyVar=$(git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT})
						
				'''
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


