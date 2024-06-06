pipeline {
    agent any                                  
    parameters{
        string(name:'Env',defaultValue:'Test',description:'Env to dep1')
    stages {
        stage('compile') {                     
            steps {
                echo 'compile the code'
            }
        }
        stage('unittest') {
            steps {
                echo 'run the test case'
            }
        }
        stage('package') {
            steps {
                echo "package the code env:${params.Env}"
            }
        }
    }
}
