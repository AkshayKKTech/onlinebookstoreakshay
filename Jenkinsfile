pipeline {  
    agent any  
    tools {
        // Must match the name configured in 'Global Tool Configuration'
        maven 'Maven3'
        // Replace 'SonarScanner' with the name you saved for your scanner tool
        sonar-scanner 'SonarScanner'
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
