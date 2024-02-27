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
                always{
                    echo "====++++always++++===="
                }
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
                always{
                    echo "====++++always++++===="
                }
                success{
                    echo "====++++Install Dependencies executed successfully++++===="
                }
                failure{
                    echo "====++++Install Dependencies execution failed++++===="
                }
        
            }
        }
    }
}