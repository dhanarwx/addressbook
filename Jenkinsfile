pipeline {
    agent any
    
    tools {
        maven 'mymvn'
    }
        

    stages {
        stage('compile') {
            steps {
                echo "compile the code }"
                sh 'mvn compile'
            }
        }
        stage('testing') {
            steps {
                echo 'test the code '
                sh 'mvn test'
            }
        }
        stage('package') {
            steps {
                echo "package the code "
                sh 'mvn package'
            }
        }
        
    }
}
