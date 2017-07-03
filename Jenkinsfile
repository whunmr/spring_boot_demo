pipeline {
    agent any

    post {
        always {
            archive "target/**/*"
            junit 'target/surefire-reports/*.xml'
        }
    }
    
    docker.image('rowanto/docker-java8-mvn-nodejs-npm').inside {
        stages {
            stage("build") {
                steps {
                    sh 'mvn clean test'
                }
            }
        }
    }
}


