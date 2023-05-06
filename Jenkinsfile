pipeline {

  agent {

    docker {

      image 'docker:latest'

      args '-v /var/run/docker.sock:/var/run/docker.sock'

    }

  }

  stages {

    stage('Build Docker image') {

      steps {

        sh 'docker build -t felsiyak/docker-react -f Dockerfile.dev .'

      }

    }

    stage('Run tests') {

      steps {

        sh 'docker run -e CI=true felsiyak/docker-react npm test'

      }

    }

  }

}


