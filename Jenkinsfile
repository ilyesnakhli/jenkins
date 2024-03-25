pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub repository
                git branch: 'main', credentialsId: 'git', url: 'https://github.com/ilyesnakhli/jenkins.git'
                  }
                          }
        


        stage('Build Image - Java') {
            when {
                changeset "Dockerfile_java"
            }
            steps {
                // Build Docker image for Scala
                sh "docker build -t java_notebook -f Dockerfile_java ."
            }
        }
                          
       stage('Build Image - Bash') {
            when {
                changeset "Dockerfile_bash"
            }
            steps {
                // Build Docker image for Bash
                sh 'docker build -t bash_notebook -f Dockerfile_bash .'
            }
        }
        
        
        

         }  
         /*post {
    success {
        rocketSend "Pipeline ${currentBuild.fullDisplayName} succeeded"
        slackSend(channel: '#jenkins-test', message: "Pipeline ${currentBuild.fullDisplayName} succeeded")
      emailext subject: "Pipeline succeeded: ${currentBuild.fullDisplayName}", 
      body: "The pipeline ${currentBuild.fullDisplayName} succeeded",
                      to: "ilyesnakhlii188@gmail.com"
    }
    failure {
        slackSend(channel: '#jenkins-test', message: 'Pipeline ${currentBuild.fullDisplayName} failed')
       emailext subject: "Pipeline Failed: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} failed. Please investigate.",
                      to: "ilyesnakhlii188@gmail.com"
    }
    
       
  }*/
         
         
}

