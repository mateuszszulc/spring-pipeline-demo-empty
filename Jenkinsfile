node {
    sh 'git remote -v'
    git url: 'https://github.com/mateuszszulc/spring-pipeline-demo-empty.git', branch: 'main'
    docker.image('maven:3-openjdk-11').inside('-v $HOME/.m2:/root/.m2') {
        stage('Build') {
            sh 'mvn clean verify'
        }
    }
}
