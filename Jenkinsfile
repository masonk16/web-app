pipeline {
    agent any

    stages {
        stage("Clone Code") {
            steps {
                echo "Cloning the code"
                git url: "https://github.com/masonk16/web-app.git", branch: "main"
            }
        }

        stage("Build") {
            steps {
                echo "Building the Docker image"
                sh "sudo docker build -t web-app https://github.com/masonk16/web-app.git"
            }
        }

        stage("Push to Docker Hub") {
            steps {
                echo "Pushing image to Docker Hub"
                withCredentials([usernamePassword(credentialsId: "dockerHub", passwordVariable: "dockerHubPass", usernameVariable: "dockerHubUser")]) {
                    sh "sudo docker tag web-app ${env.dockerHubUser}/web-app:latest"
                    sh "sudo docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                    sh "sudo docker push ${env.dockerHubUser}/web-app:latest"
                }
            }
        }

        stage ("Deploy") {
            steps {
                echo "Deploying the container"
                sh "sudo docker compose down && docker compose up -d"
            }
        }
    }
}