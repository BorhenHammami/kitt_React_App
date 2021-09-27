pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/BorhenHammami/kilt_react.git'
   
      }
    
    }
    stage('Install Packages') {
      steps {
        sh 'sudo npm install'
      }
    }
    stage('Test and Build') {
      parallel {
        stage('Run Tests') {
          steps {
            sh 'npm run test'
          }
        }
        stage('Create Build Artifacts') {
          steps {
            sh 'npm run build'
          }
       }
     
        stage('ZIP and Upload') {
          steps {
             sh '/var/lib/jenkins/workspace/copy.sh' 
      
      }
       }
      }
    }
    }    
}
