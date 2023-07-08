pipeline {
    agent any
    tools {nodejs "MyNodeJs"}
    environment {
        NODE_ENV= "production"
    }
    stages {
        stage('Dev') {
            environment{
                NODE_ENV= " devlop"
            }
            steps {
                echo NODE_ENV
                git 'https://github.com/toshallab/july23jenkin-demo.git'
                echo " Conte of file "
                sh 'cat jenkindemo.txt'
            }
        }
        stage ('build') {
            steps {
            echo NODE_ENV
            sh 'npm install'    
            }
        }
        stage ('myartifact') {
            steps {
            archiveArtifacts artifacts: '**', followSymlinks: false
            }
        }
    }
}