pipeline {
    agent any 

 tools {
        maven 'Maven'
    
    }
    
    stages {

 
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
        
        

        stage('clone repo and clean it') { 
            steps {
               
             bat "mvn clean"
            }
        }
        stage('Test') { 
            steps {
            
                bat "mvn test"
            }
        }
        stage('Deploy') { 
            steps {
                bat "mvn package"
            }
        }
    }
}
