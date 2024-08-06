pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh 'aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 992256429851.dkr.ecr.us-east-2.amazonaws.com'
                sh 'podman build -t demo .'
                sh 'podman tag demo:latest 992256429851.dkr.ecr.us-east-2.amazonaws.com/demo:latest'
                sh 'podman push 992256429851.dkr.ecr.us-east-2.amazonaws.com/demo:latest'
                // sh 'helm upgrade --install demo app --namespace demo2 --create-namespace --wait --timeout 5m'
                echo 'FINISHED'
            }
        }
    }
}
