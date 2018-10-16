pipeline {
   agent {
      label ('linux_builder')
   }
   stages{
     stage('build') {
        steps {
	   sh "pwd"
	   sh '''#!/bin/bash
	         make -j 4
	   '''
	}
     }
     stage('build_debug') {
        steps {
	   sh "pwd"
	   sh '''#!/bin/bash
	         make -j 4 -g3
	   '''
	}
     }
   }
}