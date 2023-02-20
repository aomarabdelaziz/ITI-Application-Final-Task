pipeline {
    agent { label 'jenkins-label' }
    stages {
        stage('build') {
            steps {
                script {
                    sh   """
                        docker build -t gcr.io/abdelaziz-gke/iti_graduation_project .
                        docker push gcr.io/abdelaziz-gke/iti_graduation_project
                    """
                }
            }
        }
        stage('deploy') {
            steps {
                script {
                    sh    """
                        kubectl apply -f Deployment
                    """
                }
            }
        }
    }
}