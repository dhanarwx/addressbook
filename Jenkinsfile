pipeline {
    agent none

    tools{
        jdk 'myjava'
        maven 'mymaven'
    }

    stages {
        stage('compile') {
            agent any
            steps {
                echo "compile the code "
                sh 'mvn compile'
            }
        }
        stage('unittest') {
            agent any
            steps {
                echo 'run the test case'
                sh 'mvn test'
            }
            post{
                always{
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('package') {
            agent {lable 'linux-slave'}
            steps {
                echo "package the code }"
                sh 'mvn package'
            }
        }
    }
}