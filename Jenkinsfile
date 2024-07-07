pipeline {
    agent any

    environment {
        GITHUB_CREDENTIALS = credentials('github_credentials')
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    git(
                        url: 'https://github.com/crchende/jenkinsdemo.git',
                        credentialsId: "${GITHUB_CREDENTIALS}"
                    )
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                // Add your build steps here
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh "python3 salut.py | python3 verifica_salut.py"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // Add your deploy steps here
            }
        }
    }
}
