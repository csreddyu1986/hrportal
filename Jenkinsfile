pipeline {
    agent {
        label 'docker-slave'  
    }
    tools {
        // Update the tool name to match the one defined in your Jenkins configuration
        jdk 'Java 17'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout your GitHub repository
                git 'https://github.com/sakthibazz1/hrportal.git'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    // Run SonarQube analysis using the SonarScanner
                    def scannerHome = tool 'SonarScanner' // Configure SonarScanner tool in Jenkins
                    withSonarQubeEnv('hrportal-sonarqube') {
                        sh """
                            ${scannerHome}/bin/sonar-scanner \
                            -Dsonar.projectKey=hrportal \
                            -Dsonar.sources=. \
                            -Dsonar.host.url=http://172.31.18.169:9091 \
                            -Dsonar.token=squ_5249de2dffe875f8708a43521136bb56228b04be
                        """
                    }
                }
            }
        }
        
        stage ('docker'){
            steps{ 
                sh "sudo docker-compose up --build "
            }
        }
    }
}
