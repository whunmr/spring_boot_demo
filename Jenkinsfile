pipeline {
    agent any

    post {
        always {
            archive "target/**/*"
            junit 'target/surefire-reports/*.xml'
        }
    }
    
    stage('SonarQube analysis') {
        // requires SonarQube Scanner 2.8+
        def scannerHome = tool 'SonarQubeScanner';
        withSonarQubeEnv('My SonarQube Server') {
          sh "${scannerHome}/bin/sonar-scanner"
        }
    }
}


