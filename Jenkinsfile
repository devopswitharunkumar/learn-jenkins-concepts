pipeline{
    agent {
        node {
            label 'Agent-1'
        }
    }
    environment {
        Greeting = "Hello, Good Morning"
        NAME="Arun"

        IMAGE_NAME="payment"

        IMAGE_TAG="1.0"

        AWS_REGION="us-east-1"
    } 

    parameters{
        choice(
            name:'Environment',
            choices:['DEV','QA','PROD']
        )
        string(
            name:'VERSION',
            defaultValue:'1.0'
        )
        booleanParam(
            name:'RUN_TESTS',
            defaultValue:true
	    )   
        password(
		    name:'DB_PASSWORD'
		)
            
    }

    options{
	timeout(time:1, unit:'SECONDS')
}
    
        

    stages {
        stage('Agent-Info') {
            steps {
                echo "Running From Agent-1" 
                echo "${Greeting}, ${NAME} from Agent stage"
            }
        }
        
        stage('Build') {
            steps {
                echo "This is a build stage where Build packages and download dependencies everything needed for the application"
                echo """${IMAGE_NAME}:${IMAGE_TAG}:${AWS_REGION} from build stage"""
            } 
            //for each single stage post block we can write like this
            post {
                success {
                    echo "if build stage success only this post build runs"
                }
                failure {
                    echo "if build stage fails only this post build runs"
                }
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
                echo """${IMAGE_NAME}:${IMAGE_TAG}:${AWS_REGION} from Deployment stage"""
                sleep 10
            }
        }
    }
//for total stages post block we can write like this
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