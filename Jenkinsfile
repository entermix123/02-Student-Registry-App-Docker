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
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to production'
            }
        }
}
