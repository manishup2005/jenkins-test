pipeline {
    agent none
    stages {
        stage('Checkout') {
            steps {
                echo 'Getting files from git!';
                git branch: 'main', credentialsId: 
'4ded9757-6a06-472c-9998-a3e2f19df482', url: 
'https://github.com/manishup2005/jenkins-test.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Step 1! building ';
                sh './build.sh'
            }
        }
        stage('Test') {
            steps {
                echo 'Test code!';
                sh './test.sh'
            }
        }
        stage('Quality') {
            steps {
                echo 'Running Quality Checks!';
                sh './quality.sh'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Final Deployment!';
                sh './deploy.sh'
            }
        }
    }
    post{
        always{
            echo "This will always run"
        }
        success{
            echo "This will run only when sucess"
        }
        failure{
            echo "this will run when any stage of pipeline fails"
        }
        unstable{
            echo "runs when build is unstable"
        }
        changed{
            echo "runs when there is change between prior and current"
        }
    }
}

