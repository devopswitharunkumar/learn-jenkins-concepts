pipeline{
    agent {
        node {
            label 'Agent-1'
        }
    }

    stages {
        stage('Agent-Info') {
            steps {
                echo "Running From Agent-1" 
            }
        }
        stage('Build') {
            steps {
                echo "This is a build stage where Build packages and download dependencies everything needed for the application"
            } 
        }
        stage('Testing') {
            steps {
                echo "This is a testing stage testing team will check and find bugs" 
            }
        }
        stage('Deployment') {
            steps {
                echo "This is a Deployment stage where application deployed throgh VM's" 
            }
        }
    }

    post {
        always {
            echo "Always this post build runs whether pipeline failed or success or aborted or etc.. any case "
        }
        success {
            echo "if pipeline success only this post build runs"
        }
        failure {
            echo "if pipeline failes only this post build runs"
        }
        aborted {
            echo "if pipeline aborted only this post build runs"
        }
    }
}