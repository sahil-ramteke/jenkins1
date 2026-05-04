pipeline{
    agent{label 's3'}
    stages{
        stage('install httpd'){
            steps{
                sh 'sudo yum install httpd -y'
                sh 'sudo systemctl start httpd'
                sh 'sudo systemctl enable httpd'   
            }
        }
        stage('clone repo'){
            steps{
                git branch: '2026Q2', url: 'https://github.com/sahil-ramteke/jenkins1'
            }
        }
        stage('copy file'){
            steps{
                sh 'sudo cp index.html /var/www/html/'
            }
        }
    }
}
