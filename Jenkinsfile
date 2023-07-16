pipeline {
    agent any

    tools{
        jdk 'myjava'
        maven 'mymaven'
    }

    stages {
        stage('compile') {
            steps {
                echo "compile the code "
                sh 'mvn compile'
            }
        }
        stage('unittest') {
            steps {
                echo 'run the test case'
                sh 'mvn test'
            }
        }
        stage('package') {
            steps {
                echo "package the code }"
                sh 'mvn package'
            }
        }
    }
}