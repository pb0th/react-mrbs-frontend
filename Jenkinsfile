pipeline {
    agent any
    

    tools {
        nodejs "node"
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
        // stage("Install Dependencies"){
        //     steps{
        //         echo "====++++executing Install Dependencies++++===="
        //         sh 'npm install'
        //     }
        //     post{
        //         success{
        //             echo "====++++Install Dependencies executed successfully++++===="
        //         }
        //         failure{
        //             echo "====++++Install Dependencies execution failed++++===="
        //         }
        
        //     }
        // }
        stage("Build Docker image") {
            steps{
                echo "====++++Building the application++++===="
                sh 'docker build -t mrbs-frontend:1.0 .'
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



    } 
}