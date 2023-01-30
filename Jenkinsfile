pipeline{
    agent 'any'
    stages {
        stage('git clone') {
            steps {
                sh '''
                    rm -rf DevOps
                    git clone 'https://github.com/kishorvvn/DevOps.git'
                '''
                
            }
        }
         stage('build') {
            steps {
                sh '''
                    pwd
                    ls -ll
                    cd DevOps
                    ls -ll
                    mvn clean compile 
                '''
            }
        }
        stage('test cases') {
            steps {
                sh '''
                 pwd
                    ls -ll
                    cd DevOps
                    ls -ll
                    mvn test 
                '''
            }
        }
        stage('sonar') {
            steps {
                sh '''
                 pwd
                    ls -ll
                    cd DevOps
                    ls -ll
                    mvn sonar:sonar -Dsonar.login='squ_c45b3cbea69c8d277f383e6586dfe37374edafeb' 
                '''
            }
        }
        stage('package') {
            steps {
                sh '''
                 pwd
                    ls -ll
                    cd DevOps
                    ls -ll
                    mvn package
                '''
            }
        }
        stage('upload to jfrog') {
            steps {
                sh '''
                 cd C:/Users/Kisho/.jenkins/workspace/pipelinetest1/DevOps/target 
				 curl -udeveloper:Admin-123 -T vracademy-1.0.0.jar "http://localhost:8082/artifactory/DevOps/."				
                '''
            }
        }
        
    }
}
