pipeline {
    agent any
    parameters{
        string(name:'Env',defaultValue:'Test',description:'Env to dep1')
        booleanParam(name:'executeTests',defaultValue:true,description:'decide to run tc')
    }

    stages {
        stage('compile') {
            steps {
                echo 'compile the code  '
            }
        }
        stage('testing') {
            steps {
                echo 'test the code  '
            }
        }
        stage('package') {
            steps {
                echo "package the code in env:${params.Env}"
            }
        }
    }
}
