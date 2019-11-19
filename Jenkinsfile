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
				set +x 
				workSpace=`pwd`;
				for i in `git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}` ;do 
				if python -m json.tool < $workSpace/$i  ; then 
					echo "Rohan Is Great " ; 
				else 
					echo "Rohan is Dumb ";
				fi
				done
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


