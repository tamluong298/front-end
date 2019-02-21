pipeline {
    agent any

    tools{
      maven 'NodeJS 4.8.6'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'npm install'
                sh 'npm run test'
            }
        }
        stage('Package') {
            steps {
                echo 'Deploying....'
                sh 'npm install'
                sh 'npm run package'
                archiveArtifacts artifacts: '**/target/*.zip', fingerprint: true
            }
        }
    }
}
