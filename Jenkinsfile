pipeline {
    agent any
    
    tools {
        maven 'mymvn'
    }
        

    stages {
        stage('compile') {
            agent any
            steps {
                echo "compile the code }"
                sh 'mvn compile'
            }
        }
        stage('testing') {
            agent any
            steps {
                echo 'test the code '
                sh 'mvn test'
            }
            post{
                always{
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('package') {
            agent{lable 'linux-slave'}
            steps {
                echo "package the code "
                sh 'mvn package'
            }
        }
        
    }
}
