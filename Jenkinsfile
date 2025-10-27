pipeline{
    Agent any
    stages{
        stage('build the docker image')
        steps{
            echo "build the docker image"
            bat 'docker build -t formappnew .'
        }
    }
    stages{
        stage('run')
        steps{
            echo "run the iamge"
            bat 'docker rm mycontainer || exit 0'
            bat 'docker  run -d -p 5000:5000 --name ycontainer formappnew'
        }
    }
    post{
        success{
            echo "pipeline successfully buld"
        }
        failure{
            echo "failed,check logs"
        }
    }
}