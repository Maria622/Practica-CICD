pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                echo "Compilando Aplicacion"
                sleep time: 5, unit: 'NANOSECONDS' // Pero no existe main.c
            }
        }
        stage("Test") {
            steps {
            //se escribe entre parentesis si se quiere crear un comando como ya vimos
            echo "ejecutando pruebas"
            sleep time: 3, unit: 'NANOSECONDS'
        // test.sh no es ejecutable
            }
        }
        stage("Deploy") {
            steps {
             echo "desplegando en entorno de pruebas"        
                
            }
        }
    }
    post {
        always{
            //no se le pasa un comando al parametro artifacts como tal se debe eejcutar antes
            echo 'estos pasos siempre se ejecutan'
            sh 'echo "Log de prueba" > log.txt'
            archiveArtifacts artifacts: 'log.txt', followSymlinks: false
        }
        success {
        // One or more steps need to be included within each condition's block.
        echo 'the deployment has worked'
        cleanWs()
        }
        failure {
        // One or more steps need to be included within each condition's block.
        echo 'An error has ocurred'
        }
    }
}