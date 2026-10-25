
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
                bat 'dotnet test dotnet-app.Tests/ProjectFile-Tests.csproj --logger "console;verbosity=detailed"'
            }
        }

        stage('Run Python tests') {
            steps {
                dir('python-app') {
                    bat '''
                        echo ===== Current directory =====
                        cd

                        echo ===== Python version =====
                        "C:/Users/DELL/AppData/Local/Programs/Python/Python312/python.exe" --version

                        echo ===== Files =====
                        dir

                        echo ===== Test file =====
                        type test_math_utils.py

                        echo ===== Running Python tests =====
                        "C:/Users/DELL/AppData/Local/Programs/Python/Python312/python.exe" -m unittest -v test_math_utils
                    '''
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
