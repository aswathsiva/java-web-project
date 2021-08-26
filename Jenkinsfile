pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
         stage('deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '75942c7f-37ef-48eb-9cfa-d8ae744130dc', path: '', 
                url: 'http://ec2-35-154-157-181.ap-south-1.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebproject', war: '**/java-web-project.war'
            }
        }
    }
}
