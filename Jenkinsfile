pipeline {
   agent {
      label ('master')
   }
   stages{
     stage('build') {
        steps {
	   sh "pwd"
	   sh '''#!/bin/bash
	         /usr/bin/make
	   '''
	}
     }
   }
}