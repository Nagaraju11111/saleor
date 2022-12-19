pipeline {
    agent { label 'NODE' }
    triggers { pollSCM ('* * * * *') }
    stages {
        stage ('vcs') {
            steps {
                git url: 'https://github.com/Nagaraju11111/react-storefront.git',
                    branch: 'main'
            }
        }
        stage ('dockerimagebuild') {
            steps {
               sh 'docker image build -t storefront:1.0 .'
               sh 'docker image tag storefront:1.0 9052171017/storefront:1.0'
               sh 'docker image push 9052171017/storefront:1.0'
            }
        }
    }
}