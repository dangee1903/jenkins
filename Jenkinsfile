pipeline {
    agent any
    tools {
        maven 'Maven 3.9.0' 
    }
    stages {
        stage('Clone stage') {
            steps {
                git 'https://github.com/dangee1903/jenkins.git'
            }
        }
        stage('Build stage') {
            steps {
                // This step should not normally be used in your script. Consult the inline help for details.
                withDockerRegistry(credentialsId: '33c815c1-0739-48b6-b59d-275aa6fb962a', url: 'https://index.docker.io/v1/', toolName: 'docker') {
                    // some block
                    sh 'docker build -t axiton1994/nextjs:latest .'
                    sh 'docker push -t axiton1994/nextjs:latest'
                }
            }
        }
    }
}