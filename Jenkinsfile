pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                 withCredentials([usernamePassword(credentialsId: 'esraa-docker', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                     sh """
                          docker login -u $USERNAME -p $PASSWORD
                          docker build ./Application/Dockerfile -t esraazizo/esraa-go-app:${BUILD_NUMBER}
                          docker push esraazizo/esraa-go-app:${BUILD_NUMBER}
                     """
                 }
            }
        }
    }
}
