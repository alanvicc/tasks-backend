pipeline {
    agent any

    stages {
        stage('Build Backend') {
            steps {
                bat 'mvn clean package -DskipTests=true'
            }
        }
                stage('Teste de Unidade') {
            steps {
                bat 'mvn test'
            }
        }
    }
}