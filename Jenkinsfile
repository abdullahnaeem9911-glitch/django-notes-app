@Library("shared") _
pipeline{
    agent { label "agent" }
    
    stages{
        
        stage("code"){
            steps{
                script{
                    clone("https://github.com/abdullahnaeem9911-glitch/django-notes-app","main")
                }
            }
        }
        stage("build"){
            steps{
                script{
                    docker_build("django_app","latest","abdu11ah75")
                }
            }
        }
        stage("dockerHub push"){
            steps{
                script{
                    docker_push("django_app", "latest", "abdu11ah75")
                }
            }
        }
        stage("deploy"){
            steps{
                echo "this is deploying the code"
                sh "docker compose up -d"
            }
        }
    }
}
