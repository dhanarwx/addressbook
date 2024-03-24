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
        stage('testing') {
            when{
                expression{
                    params.executeTests == true
                }
            }
            steps {
                echo 'test the code  '
            }
        }
        stage('package') {
            steps {
                echo "package the code in env:${params.Env}"
            }
        }
        stage('package') {
            input{
                message "provide approval for prod"
                ok "deploy to prod"
                parameters{
                    booleanParam(name:'DEPLOYTOPROD',defaultValue:false,description:'decide to deloy on prod')
                }
            }
            steps {
                echo "package the code in env:${params.Env}"
            }
        }
    }
}
