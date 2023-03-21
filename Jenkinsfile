pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'echo "******Building a docker image*****"'
                sh 'docker --version'
                sh 'sudo docker build -t dockerimage ./'
            }
        }
        stage('run'){
            steps{
                sh 'echo "Run Stage"'
                sh 'sudo docker images'
                sh 'sudo docker run -itd --name dockercontainer dockerimage'
            }
        }
        stage("remove"){

            steps{
                sh 'echo "removing container"'
                sh 'sudo docker rm -f dockercontainer'
                sh 'sudo docker system prune -af'
            }
        }
        
    }
}
