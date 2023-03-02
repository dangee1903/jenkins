pipeline {
    agent any
    stages {
        stage('Initialize') {
            steps{
                script {
                    def dockerHome = tool 'docker'
                    env.PATH = "${dockerHome}/bin:${env.PATH}"
                }
            }
        }
        stage('Clone stage') {
            steps {
                git 'https://github.com/dangee1903/jenkins.git'
            }
        }
        stage('Build stage') {
            steps {
                // This step should not normally be used in your script. Consult the inline help for details.
                withDockerRegistry(credentialsId: '659f37e2-e2ac-4afd-8b7a-ac137d3a9bec', toolName: 'docker', url: 'https://index.docker.io/v1/') {
                    // some block
                    sh 'docker build -t axiton1994/nextjs:latest .'
                    sh 'docker push -t axiton1994/nextjs:latest'
                }
            }
        }
    }
}