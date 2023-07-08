pipeline {
    agent any
    tools {nodejs "MyNodeJs"}
    environment {
        NODE_ENV= "production"
    }
    stages {
        stage('Dev') {
            environment{
                NODE_ENV= " develop"
            }
            steps {
                echo NODE_ENV
                git 'https://github.com/neetagithub123/jenkingitrepo.git'
                echo " Content of file "
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