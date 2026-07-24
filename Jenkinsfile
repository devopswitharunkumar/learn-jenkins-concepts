pipeline{
    agent Agent-1

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
}