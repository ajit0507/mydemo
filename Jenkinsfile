pipeline {
    agent any 

 tools {
        maven 'Maven'
    
    }
    
    stages {

 
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
        
        

        stage('clone repo and clean it') { 
            steps {
              
            // bat "git clone https://github.com/ajit0507/mydemo.git" 
             bat "mvn clean -f mydemo"
            }
        }
        stage('Test') { 
            steps {
            
                bat "mvn test -f mydemo"
            }
        }
        stage('Deploy') { 
            steps {
                bat "mvn package -f mydemo"
            }
        }
    }
}
