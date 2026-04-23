pipeline {  
    agent any  
    tools {
        // Must match the name configured in 'Global Tool Configuration'
        scannerHome = tool 'SonarScanner' 
    }
    stages {  
        stage("git_checkout") {  
            steps {  
                echo "cloning repository" 
                // Actual checkout logic goes here
                echo "repo cloned successfully"  
            }  
        } 
        stage("SonarQube Analysis") {
            steps {
                // 'SonarQube' must match the server name in 'Configure System'
                withSonarQubeEnv('SonarQube') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}
