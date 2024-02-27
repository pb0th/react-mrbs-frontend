pipeline {
    agent any
    

    tools {
        nodejs "node"
    }

    stages {
        stage("Checkout"){
            steps{
                echo "====++++executing Checkout++++===="
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
        stage("Install Dependencies"){
            steps{
                echo "====++++executing Install Dependencies++++===="
                sh 'npm install'
            }
            post{
                success{
                    echo "====++++Install Dependencies executed successfully++++===="
                }
                failure{
                    echo "====++++Install Dependencies execution failed++++===="
                }
        
            }
        }
        stage("Build") {
            steps{
                echo "====++++Building the application++++===="
                sh 'npm run build'
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
        stage("Deploy to NGINX") {
            steps {
                echo "====++++Deploying the application to NGINX++++===="
                echo "====++++Copying the build folder to /var/www/html/apps/ ++++===="
                sh " cp -r build/* /var/www/html/apps/"
            }
            post {
                success {
                    echo "====++++Deployment to Nginx completed successfully++++===="
                }
                failure {
                    echo "====++++Deployment to Nginx failed++++===="
                }
            }
        }
    } 
}