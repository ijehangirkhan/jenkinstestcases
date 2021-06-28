@Library("PythonLibrary") _
def branch = ${BRANCH_NAME}
pipeline {
    agent any
    stages {
    
        // Run Python File
        stage('Run Python File') {
        steps{  
            script {
                        sh 'python3 main.py'
                sh "echo ${env.BRANCH_NAME}"
            }
            }
        }
      
      
    }
    
    post {
        success {
            script {
                if ( env.BRANCH_NAME == 'master')
                slackSuccess()
            }
           
        }
        failure {
            script {
                if ( env.BRANCH_NAME == 'master')
                slackFailure()
            }
        }
    }

}
