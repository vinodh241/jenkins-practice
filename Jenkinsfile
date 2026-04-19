pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        MY_APP_NAME = "DEV"
        DB_NAME     = "DEV_APP_01"
        DB_IP       = "10.0.0.1"
        DB_HOST     = "DEV_APP_01"
    }
    options{
        timeout(time: 10, unit: 'SECONDS')
    }
     // Build 
    stages {
        stage('Checkout'){
            steps{
                script{
                    sh """
                        echo "Hello CheckOut"
                        sleep 10 
                        env 
                    """
                }
            }
        }
        stage('Build'){
            steps{
                echo 'Building...'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploy....'
            }
        }
    }
    post{
        always{
            echo 'Hello-world Pipeline job successfull -when its failed or success'
           // deleteDir()
        }
        success{
            echo 'Hello-world successfull condition'
        }
        failure{
            echo 'Hello-world failure condition'
        }
    }
}