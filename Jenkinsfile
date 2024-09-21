pipeline {
    agent any
    stages{
        stage('build project'){
            steps{
                git url:'https://github.com/ranjitha-narayana/FinanceDemo/', branch: "master"
                sh 'mvn clean package'
              
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t kuberanjitha/staragileprojectfinance:v1 .'
                    sh 'docker images'
                }
            }
        }
         
        
     stage('Deploy') {
            steps {
                sh 'sudo docker run -itd --name My-first-containe-demo -p 8083:8081 kuberanjitha/staragileprojectfinance:v1'
                  
                }
            }
        
    }
}
