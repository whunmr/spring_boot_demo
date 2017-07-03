pipeline {
    agent any

    post {
        always {
            archive "target/**/*"
            junit 'target/surefire-reports/*.xml'
        }
    }
    
    stages {
        stage("build") {
            steps {
                sh 'mvn clean test'
            }
        }
    }
}


