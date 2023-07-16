pipeline {
    agent any

    parameters{
        string(name:'Env',defaultValue:'Test',description:'Env to dep1')
        booleanParam(name:'executeTests',defaultValue:true,description:'decide to run tc')
        choice(name: 'APPVERSION',choices:['1.1','1.2','1.3'])
    }

    stages {
        stage('compile') {
            steps {
                echo "compile the code ${params.APPVERSION}"
            }
        }
        stage('unittest') {
            when{
                expression{
                    params.executeTests == true
                }
            }
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