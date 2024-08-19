pipeline {
    agent any
    
    stages {
        stage('One') {
            steps {
                echo 'This is stage one'
            }
        }
        
        stage('Two') {
            steps {
                input message: 'Do you want to proceed?'
            }
        }
        
        stage('Three') {
            when {
                not {
                    branch 'main'
                }
            }
            steps {
                echo "Hello"
            }
        }
        
        stage('Four') {
            parallel {
                stage('Unit Test') {
                    steps {
                        echo 'Running the unit test'
                    }
                }
                
                stage('Integration Test') {
                    steps {
                        echo 'Running the integration test'
                    }
                }
            }
        }
    }
}
