pipeline {
    agent none 
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'boto3-image' 
                }
            }
            steps {
                sh 'python -m athena.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*') 
            }
        }
    }
}