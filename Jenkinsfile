pipeline {

    agent any

    stages {

        stage('Build Maven') {

            steps {

                sh 'mvn clean package'

            }

        }

        stage('Build Docker Image') {

            steps {

                sh 'docker build -t java-devops-app .'

            }

        }

        stage('Deploy Container') {

            steps {

                sh 'docker stop java-container || true'

                sh 'docker rm java-container || true'

                sh 'docker run -d --name java-container java-devops-app'

            }

        }

    }

}
