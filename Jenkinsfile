node {
    sh 'git remote -v'
    sh 'pwd'
    sh 'ls -la'
    docker.image('maven:3-openjdk-11').inside('-v $HOME/.m2:/root/.m2') {
        stage('Build') {
            sh 'pwd'
            sh 'ls -la'
            sh 'mvn clean verify'
        }
    }
}
