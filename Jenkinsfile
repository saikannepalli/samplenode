pipeline{
    agent any
   
        stage('Build Docker Image'){
	  steps{
	     sh "sudo docker build -t saikannepalli/samplenode:${BUILD_ID} ."   //when we run docker in this step, we're running it via a shell on the docker build-pod container
                        }
       }
 // Pushing the Docker Image to DockerHub   
     stage('Push Docker Image'){
	steps{
//Docker Hub Credentials
        withCredentials([string(credentialsId: 'sai-dockerpwd', variable: 'sai-dockerpwd')]) {
          sh "sudo docker login -u saikannepalli -p ${sai-dockerpwd}"
          sh "sudo docker push saikannepalli/samplenode:${BUILD_ID}"
	              }
           }
       }  
	     
    
     }
