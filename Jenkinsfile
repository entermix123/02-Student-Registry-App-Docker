pipeline {
    agent any
    stages {
        stage('NPM Install') {
            steps {
                bat 'npm install'
            }
        }
        stage('Parallel Tasks') {
            parallel {
                stage('Run npm audit tests') {
                    steps {
                        bat 'npm audit'
                    }
                }
                stage('Execute Tests') {
                    steps {
                        bat 'npm test'
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploy to staging'
            }
        }
        stage('Approval for Production') {
            steps {
                script {
                    input message: 'Approve deployment to production?', ok: 'Deploy'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to production'
            }
        }
    }
}
