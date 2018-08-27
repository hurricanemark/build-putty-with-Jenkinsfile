# Using c-code from source forge to demonstrate Jenkins pipeline and Free-style builds #
## Source: 
This open source is originally from sourceforge.com

## Pre-requisites: 
gnu-make, gcc
## Native build:
	cd unix
	./configure
	make
	make test
	make install

## Jenkins scripts: 
Jenkinsfile

## Note
'''
Alternatively, source repo can be on an ftp site or remote directory/URL.
In which case, it can be retrieved using curl command, or SSHAgent/SFTP plugins.
'''

** Example:  Using parameterized variables --  AUTH_REQUIRED bool; USERID, PASSWD, SOURCE_URL string.
	#!/bin/bash
	if test $AUTH_REQUIRED = 'true'; then
            curl -u ${USERID}:${PASSWD} -O ${SOURCE_URL}
        else
            curl -Ol ${SOURCE_URL}
        fi
