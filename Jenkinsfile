@Library("shared") _
pipeline {
    agent { label "vinod" }

    stages {
        
        stage("Hello"){
            steps{
                hello()
            }
        }
        stage('clone') {
            steps {
                script{
                    clone("https://github.com/LondheShubham153/django-notes-app.git", "dev")
                }
            }
        }
        stage("Build") {
            steps{
                script{
                    docker_build("notes-app", "latest", "prakashghorpade2001")
                }
            }
        }
        stage("Push"){
            steps{
                script{
                    docker_push("notes-app", "latest")
                }
            }
        }
        stage("Deploy"){
            steps{
                    deploy()
            }
        }
        
    }
}
