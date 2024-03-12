pipeline {
    agent {
        docker {
            image 'cypress/base:14.17.0'
            args '-v /var/run/docker.sock:/var/run/docker.sock' // Para permitir a execução de Docker dentro do contêiner
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install' // Instala as dependências do Cypress
            }
        }
        stage('Test') {
            steps {
                sh 'npm run test' // Executa os testes Cypress
            }
        }
        stage('Cleanup') {
            steps {
                sh 'npm run cleanup' // Qualquer ação de limpeza necessária
            }
        }
    }
}
