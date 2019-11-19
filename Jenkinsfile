pipeline {
	agent any 
	stages {
		stage ('Verify') {
			steps {
				sh '''
				errorStatus=0
				#!/bin/sh
				set +x +e
				workSpace=`pwd`;
				for i in `git diff-tree --no-commit-id --name-only -r ${GIT_COMMIT}` ;do 
				python -m json.tool < $workSpace/$i &>/dev/null
				if [ $? -eq 0 ] ; then
						echo "$i : is a Valid json File  " ;
					else 
						echo "$i : is Not a Valid json File  ";
						errorStatus=1
                                	fi
			      	done
				if [ $errorStatus -eq 0 ] ; then continue ; else exit 1 ; fi  
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


