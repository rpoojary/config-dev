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
				set +x +e
				workSpace=`pwd`;
				for i in `git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}` ;do 
				python -m json.tool < $workSpace/$i 2>&1
				if [ $? -eq 0 ] ; then
						echo "$i : is a Valid json File  " ;
					else 
						echo "$i : is Not a Valid json File  ";
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


