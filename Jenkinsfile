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
				sh '''
				#!/bin/sh
				#MyVar=$(git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT})
				#echo "$MyVAR"
				for i in `git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}` ;do echo $i ; done
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


