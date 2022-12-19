pipeline {
    agent { label 'NODE' }
    triggers { pollSCM ('* * * * *') }
    stages {
        stage ('vcs') {
            steps {
                git url: 'https://github.com/Nagaraju11111/saleor.git',
                    branch: 'main'
            }
        }
        stage ('dockerimagebuild') {
            steps {
               sh 'docker image build -t saleor:1.0 .'
               sh 'docker image tag sdb:1.0 9052171017/saleor:1.0'
               sh 'docker image push 9052171017/saleor:1.0'
            }
        }
    }
}