pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Build your application here
                sh 'npm install'
                sh 'npm run test'
                sh 'npm run build'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                // Deploy your application to production here
                sh 'mkdir -p production'
                sh 'cp -R build/* production/'
            }
        }

        stage('Notification') {
            steps {
                sh 'git tag -a DEPLOYED -m "Application successfully deployed"'
                sh 'git push origin DEPLOYED'
            }
        }
    }
}