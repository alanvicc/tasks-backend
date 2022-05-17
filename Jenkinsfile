pipeline {
    agent any

    stages {
        stage('Build Backend') {
            steps {
                bat 'mvn clean package -DskipTests=true'
            }
        }
                stage('Testes de Unidade') {
            steps {
                bat 'mvn test'
            }
        }
                stage('Analise Sonar') {
                    environment {
                        scannerHome = tool 'SONAR_SCANNER'
                    }
            steps {
                    withSonarQubeEnv('SONAR_LOCAL') {

                bat "${scannerHome}/bin/sonar-scanner -e -Dsonar.projectKey=DeployBackEnd -Dsonar.host.url=http://localhost:9000-Dsonar.login=fa69b1805c237a69c6aedd7863a547107981b8d2 -Dsonar.java.binaries=target -Dsonar.coverage.exclusions=**/.mvn/**,**/src/test/**,**/model/**,**Application.java"
                    }
            }
        }
    }
}

