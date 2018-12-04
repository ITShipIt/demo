pipeline {
    agent any
    stages {
        stage('---clean---') {
            steps {
                sh "cd ~/"
                sh "ContainerId=`docker container ls -q`"
                sh "docker container stop \$ContainerId"
                sh "docker rm \$(docker ps -aq)"
                sh "cd /var/lib/jenkins/workspace/PipelineDemo3/"
            }
        }
        stage('--Docker Image--') {
            steps {
                sh "docker build -t demo2 ."
                sh "aws ecr batch-delete-image --repository-name demo --image-ids imageTag=recent"
                sh "docker tag demo2:latest 912379940316.dkr.ecr.us-west-2.amazonaws.com/demo:recent"
                sh "docker push 912379940316.dkr.ecr.us-west-2.amazonaws.com/demo:recent"
            }
        }
        stage('--Deploy--') {
            steps {
                sh "docker pull 912379940316.dkr.ecr.us-west-2.amazonaws.com/demo:recent"
                sh "docker run -d -p 4000:80 912379940316.dkr.ecr.us-west-2.amazonaws.com/demo:recent"
            }
        }
    }
}