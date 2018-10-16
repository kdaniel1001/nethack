pipeline {
   agent {
      label ('linux_builder')
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