pipeline {
    agent any
    tools {nodejs "mynodejs"}
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
                sh 'cat jenkinsdemo.txt'
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