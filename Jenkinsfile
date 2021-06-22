pipeline {
    agent any
    parameters {
        string(name: 'result', description: 'Result of Python')
    }
    stages {
    
        // Run Python File
        stage('Run Python File') {
        steps{  
            script {
                params.result = sh (returnStdout: true, script: 'python3 main.py').trim()
            }
            }
        }
      
      
    }

}
