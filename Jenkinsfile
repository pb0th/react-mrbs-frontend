pipeline {
    agent any
    

    tools {
        nodejs "node"
    }

    environment {
        IMAGE_NAME = 'mrbs-frontend'
        CONTAINER_NAME = 'mrbs-frontend-container'
    }

    stages {
        stage("Checkout"){
            steps{
                echo "====++++executing Checkout++++===="
                checkout scm
            }
            post{

                success{
                    echo "====++++Checkout executed successfully++++===="
                }
                failure{
                    echo "====++++Checkout execution failed++++===="
                }
        
            }
        }

        stage("Build Docker image") {
            steps{
                echo "====++++Building the application++++===="
                sh 'docker build -t ${IMAGE_NAME}:1.0 .'
            }
            post {
                success{
                    echo "====++++Built successfully++++===="
                }
                failure{
                    echo "====++++Built failed++++===="
                }
            }
        }

        stage("Run Docker Image") {
            steps{
                echo "====++++Building the application++++===="

            }
            post {
                success{
                    echo "====++++Run successfully++++===="
                }
                failure{
                    echo "====++++Run failed++++===="
                }
            }
        }


        // stage("Push image to DockerHub") {
        //     steps {
        //         withCredentials([usernamePassword(credentialsId: 'DOCKER_HUB_CREDENTIALS', usernameVariable: 'DOCKER_HUB_USERNAME', passwordVariable: 'DOCKER_HUB_PASSWORD')]) {
        //             sh 'docker login -u $DOCKER_HUB_USERNAME -p $DOCKER_HUB_PASSWORD'
        //             sh 'docker tag mrbs-frontend:1.0 pb0th/mrbs-frontend:1.0'  
        //             sh 'docker push pb0th/mrbs-frontend:1.0'
        //             sh 'docker logout'
                     
        //         }
        //     }
        // }



    } 
}