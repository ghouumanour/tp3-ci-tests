
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ghouumanour/tp3-ci-tests.git'
            }
        }

        stage('Run .NET tests') {
            steps {
                dir('dotnet-app.Tests') {
                    bat '"C:\\Program Files\\dotnet\\dotnet.exe" test ProjectFile-Tests.csproj'
                }
            }
        }

        stage('Run Python tests') {
            steps {
                    bat '"C:\Users\DELL\AppData\Local\Programs\Python\Python312\python.exe" -m unittest -v'
                 }
             }
        }
    }

    post {
        always {
            echo 'Pipeline finished !!!'
        }
    }
}
