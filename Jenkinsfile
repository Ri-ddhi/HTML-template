pipeline {
    agent any
    stages {
        stage('Cleanup') {
            steps {
                // This stops any old version of your site before starting the new one
                sh 'docker stop my-html-site || true'
                sh 'docker rm my-html-site || true'
            }
        }
        stage('Deploy to Docker') {
            steps {
                // This starts your site in a fresh container
                sh 'docker run -d -p 80:80 --name my-html-site -v $(pwd):/usr/share/nginx/html nginx'
            }
        }
    }
}
