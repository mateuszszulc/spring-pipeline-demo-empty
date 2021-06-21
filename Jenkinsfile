pipeline {
    agent none
    stages {
        stage('Verify PR') {
            agent {
                docker {
                    image 'maven:3-openjdk-11'
                    label "docker-agent"
                }
            }
            steps {
                script {
                    try {
                        sh 'mvn clean verify'
                    } catch (Exception e) {
                        currentBuild.result = 'FAILED'
                        error("Verify PR Failed");
                    }
                }
                script {
                    currentBuild.result = 'SUCCESS'
                }
            }
        }
    }
}
