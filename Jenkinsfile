pipeline {
    agent any
    environment {
        IMAGE_NAME = "my-nginx"
        CONTAINER_NAME = "nginx-container"
        KUBECONFIG = "/home/jenkins/.kube/config"  // ✅ Add this line
      }
    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Stop & Remove Old Container') {
            steps {
                script {
                    sh '''
                    docker ps -q --filter "name=$CONTAINER_NAME" | grep -q . && docker stop $CONTAINER_NAME && docker rm $CONTAINER_NAME || true
                    '''
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 80:80 --name $CONTAINER_NAME $IMAGE_NAME'
            }
        }

        stage('Deploy to K3s') {
            steps {
                sh '''
                kubectl apply -f deployment.yaml
                kubectl apply -f service.yaml
                '''
            }  // ✅ Yeh missing closing bracket add kiya
        }  // ✅ Yeh missing closing bracket add kiya

    }  // ✅ Yeh missing closing bracket add kiya
}
