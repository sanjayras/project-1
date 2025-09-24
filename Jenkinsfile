pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/sanjayras/project-1.git'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with sanjay'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with sanjay'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with sanjay'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with sanjay'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
