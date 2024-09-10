pipeline {   
    agent any 
    stages {
        stage ('Construir entorno') {
            agent {
                docker {
                    image 'node:20.11.1-alpine3.19'
                    reuseNode true
                }
            }
            stages {
                stage ('Instalar dependencias') {            
                    steps {
                        sh 'npm install'
                    }                   
                }
            }
            stages {
                stage ('Ejecucion de test') {
                    steps {
                        sh 'npm run test'
                    }
                }
            }

        }
        stage ('Ejecutar') {
            steps {
                sh 'docker build -t backend-base-devops:lastest .'
            }

        }
        

    }
}