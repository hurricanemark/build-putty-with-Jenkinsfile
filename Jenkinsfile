pipeline {
    agent { 
        node { 
            label 'AzureSLES-13.91.130.158' 
        } 
    } 

    stages {
        stage ('Build') {
            steps {
                sh 'cd putty-0.67/unix; ./configure' 
            }
            steps {
                sh 'make' 
            }
            steps {
                sh 'make test' 
            }
            steps {
                sh 'make install' 
            }
        }
    }
}
