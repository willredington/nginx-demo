pipeline {
    agent any

    environment {
        HELLO = credentials('HELLO')
    }

    stages {
        stage('Hello') {
            steps {
                sh 'aws ecr get-login-password --region us-east-1 | podman login --username AWS --password-stdin 326953433073.dkr.ecr.us-east-1.amazonaws.com'
                sh 'podman build -t demo .'
                sh 'podman tag demo:latest 326953433073.dkr.ecr.us-east-1.amazonaws.com/demo:latest'
                sh 'podman push 326953433073.dkr.ecr.us-east-1.amazonaws.com/demo:latest'
                sh 'helm upgrade --install demo app --namespace demo1 --create-namespace --wait --timeout 5m'
                echo 'FINISHED'
            }
        }
    }
}
