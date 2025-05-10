pipeline {
    agent any
    stages {
        stage('Checkout') 
        {
            steps { git branch: 'dev', url: 'https://github.com/shekardevopsaws/Multi-branch-pipeline.git' }
        }
        stage('Build') {
            steps { 
                sh 'mvn clean package' 
            }
        }
        stage('Unit Test') 
        {
            steps { 
                sh 'mvn test' 
            }
        }
        stage('Code Scan') 
        {
            steps 
            { 
                sh 'mvn sonar:sonar'
            }
        }
        stage('Deploy to Nexus-artifacts') {
            steps {
                sh 'mvn deploy'
                
            }
        }
    }
}
