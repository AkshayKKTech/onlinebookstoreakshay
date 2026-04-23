pipeline {  
    agent any  
    tools {
        // Ensure 'Maven3' matches the name in Manage Jenkins > Tools
        maven 'MAVEN_HOME
    }
    stages {  
        stage("git_checkout") {  
            steps {  
                // This checks out the code from the URL you configured in the job
                checkout scm
                echo "repo cloned successfully"  
            }  
        } 
        stage("SonarQube Analysis") {
            steps {
                // 'SonarQube' must match the Server Name in Manage Jenkins > System
                withSonarQubeEnv('SonarQube') {
                    // Maven will automatically use its built-in sonar plugin
                    sh "mvn sonar:sonar"
                }
            }
        }
    }
}

