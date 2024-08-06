pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh 'podman build -t demo .'
                // sh 'helm upgrade --install demo app --namespace demo2 --create-namespace --wait --timeout 5m'
                echo 'FINISHED'
            }
        }
    }
}
