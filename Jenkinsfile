pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh  'docker build -t  wordpress_test .'
            }
        }
        stage('Push image') {
         steps {
           withDockerRegistry([url: "https://415950205191.dkr.ecr.us-east-1.amazonaws.com/wordpress_test",credentialsId: "ecr:us-east-1:AWS_ECR_CREDENTIALS"]) 
           sh 'docker tag wordpress_test:latest 415950205191.dkr.ecr.us-east-1.amazonaws.com/wordpress_test:latest'
           sh 'docker push 415950205191.dkr.ecr.us-east-1.amazonaws.com/wordpress_test:latest'
               }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post
    {
        always
        {
            // make sure that the Docker image is removed
            sh "docker rmi $IMAGE | true"
        }
    }
} 






