pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Build your application here
                sh 'npm install'
                sh 'npm run build'
            }
        }
        
        stage('Deploy to Production') {
            when {
                changeset "refs/remotes/origin/main"
            }
            steps {
                // Deploy your application to production here
                sh 'mkdir -p production'
                sh 'cp -R dist/* production/'
            }
        }
    }
}