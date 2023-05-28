pipeline {
    agent {
        label 'maven'
    }

    stages {
        stage('pooling') {
            steps{
                git branch: 'main', url: 'https://github.com/DevOpsThoughts/shopizer.git'
            }
        }
        stage('package'){
            steps{
                mvn clean package
            }
        }

        stage('archive-artifact'){
            steps{
                archiveArtifacts artifacts: '**/target/*.jar', followSymlinks: false
            }
        }

    
    }
}