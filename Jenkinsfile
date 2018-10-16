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
              cd src\n
	      sed -i 's/CFLAGS = -O2 -fomit-frame-pointer/CFLAGS = -g/g' Makefile\n
	      cd ../util\n
	      sed -i 's/CFLAGS = -O2 -fomit-frame-pointer/CFLAGS = -g/g' Makefile\n
	      cd ..\n
              make -j 4 \n
	   '''
	}
     }
   }
}