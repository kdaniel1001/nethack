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
                 ls -alth src/nethack
		 sudo make install
		 sudo tar cvzf nethack.tgz /data/games
           '''
	}
     }
     stage('build_debug') {
        steps {
	   sh "pwd"
	   sh '''#!/bin/bash
              make spotless
              cd src
	      sed -i 's/CFLAGS = -O2 -fomit-frame-pointer/CFLAGS = -g/g' Makefile
	      cd ../util
	      sed -i 's/CFLAGS = -O2 -fomit-frame-pointer/CFLAGS = -g/g' Makefile
	      cd ..
              make -j 4
              ls -alth src/nethack
	      sudo make install
	      sudo tar cvzf nethack.tgz /data/games
	   '''
	}
     }
   }
}