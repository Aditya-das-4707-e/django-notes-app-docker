@Library("Shared") _
pipeline {
    agent any
    stages{
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/Aditya-das-4707-e/django-notes-app-docker.git", "dev")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("notes-app-demo","latest","aditya81888")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("notes-app-demo","latest","aditya81888")
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "this is deploying the code"
                sh "docker compose down && docker compose up -d"
            }
        }
    }
}
