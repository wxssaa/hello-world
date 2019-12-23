pipeline {
   agent any

   stages {
      stage('Build') {
         steps {
            // Get some code from a GitHub repository
            // git 'https://github.com/wxssaa/hello-world.git'

            // Build docker image
            // sh 'docker image build -t hello-world:0.0.2 .'
            sh 'echo "ignore build"'
            
            // Push docker image
            // sh 'docker login --username=wxssaa --password=Lingerwx@123'
            // sh 'docker image tag hello-world:0.0.2 wxssaa/hello-world:0.0.2'
            // sh 'docker image push wxssaa/hello-world:0.0.2'
         }
      }
      stage('Deploy') {
         steps {
            // Pull docker image
            // sh 'docker image pull wxssaa/hello-world:0.0.2'
            
            // Remove old container
            // sh 'docker rm -f hello-world || echo "Container app already deleted."'
            
            // Run docker image
            sh '/snap/bin/kubectl apply -f deployment.yaml'
            sh '/snap/bin/kubectl apply -f service.yaml'
         }
      }
      stage('Test') {
         steps {
            // Print hello world, using docker container ip
            sh 'curl http://127.0.0.1:32390/'
         }
      }
   }
}