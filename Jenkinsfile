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
    options {
        timeout(time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Jenkins', description: 'Who to say hello to')
        choice(name: 'ENV', choices: ['dev', 'qa', 'prod'], description: 'Target Environment')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Run tests?')
    }
    stages {
        stage('Checkout') {
            steps {
                script {
                    sh """
                        echo "Hello CheckOut"
                        sleep 10
                        env
                        echo "Hello ${params.PERSON}, deploying to ${params.ENV}"
                    """
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying....'  // ✅ moved inside script block
                }
            }
        }
    }
    post {
        always {
            echo 'Hello-world Pipeline job'
            // deleteDir()
        }
        success {
            echo 'Hello-world job executed successfully'
        }
        failure {
            echo 'Hello-world failure condition'
        }
    }
}