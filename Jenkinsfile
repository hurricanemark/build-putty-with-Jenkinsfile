pipeline {
    agent { 
        node { 
            label 'AzureSLES-13.91.130.158' 
        } 
    } 

    stages {
        stage ('Clone') {
            steps {
                git url: 'https://github.com/hurricanemark/putty-0.67.git' 
            }
        }
        stage ('Build') {
            steps {
                sh 'cd putty-0.67/unix; ./configure' 
                sh 'make' 
            }
        }
        stage ('Test') { 
            steps {
                sh 'make test' 
            }
        }
        stage ('Install') {
            steps {
                sh 'make install' 
            }
        }
        stage ('Clean') {
            steps {
                sh 'make clean' 
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'Output  will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
