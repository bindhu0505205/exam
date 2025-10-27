pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building  Docker Image'
                bat 'docker build -t formappnew .'
            }
        }

        stage('Run') {
            steps {
                echo 'Run application in Docker container'
                bat 'docker rm -f mycontainer || exit 0'
                bat 'docker run -d -p 5000:5000 --name mycontainer formappnew'
            }
        }
    }

    post {
        success {
            echo 'Pipeline sucessfully build.'
        }
        failure{
            echo 'failed check logs.'
        }
    }
}
