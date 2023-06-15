pipeline {
    agent { label 'slave-one' }
    stages {
        stage('build') {
            steps {
                 withCredentials([usernamePassword(credentialsId: 'esraa-docker', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                     sh """
                          docker login -u $USERNAME -p $PASSWORD
                          cd ./Application
                          docker build . -t esraazizo/esraa-go-app:${BUILD_NUMBER}
                          docker push esraazizo/esraa-go-app:${BUILD_NUMBER}
                          cd ..
                     """
                 }
            }
        }
    }
}
