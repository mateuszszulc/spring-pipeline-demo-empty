pipeline {
    agent none
    stages {
        stage('Test') {
            agent {
                docker {
                    image 'maven:3-openjdk-11'
                }
            }
            steps {
                script{
                    try {
            sh 'pwd'
            sh 'ls -la'
            sh 'mvn clean verify'
                    } catch(Exception e){
                        currentBuild.result = 'FAILED'
                        notifyBitbucket()
                        error("Tests failed")
                    }
                }
            }
        }
    }
}
