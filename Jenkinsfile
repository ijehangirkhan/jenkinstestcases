@Library("PythonLibrary") _
pipeline {
    agent { label 'slave1' }
    stages {
    
        
        // Run Python File
        stage('Run Python File') {
        steps{  
            script {
                        sh 'python3 main.py'
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
