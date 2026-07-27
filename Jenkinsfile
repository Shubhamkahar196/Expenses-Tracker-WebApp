pipeline {
    agent any
    stages{
        stage("Checkout code"){
            steps{
                git url: "https://github.com/Shubhamkahar196/Expenses-Tracker-WebApp.git",branch: "main"
            }
        }
        stage("Build & Deploy with Docker Compose"){
            steps{
                sh "docker compose down"
                sh "docker compose up --build -d"
            }
        }
    }
    post{
        always{
            sh "docker image prune -f"
        }
    }
}
