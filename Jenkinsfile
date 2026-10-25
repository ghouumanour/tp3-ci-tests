
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
                dir('python-app') {
                    bat 'python -m unittest -v'
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
