pipeline {
    agent any

    stages {
        stage('Docker Push') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'jenkins-devops', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                        sh '''
                            export DOCKER_HOST=tcp://host.docker.internal:2375
                            docker login -u $USERNAME -p $PASSWORD
                            docker push damdur/node-web-app
                        '''
                    }
                }
            }
        }   
    }
}
