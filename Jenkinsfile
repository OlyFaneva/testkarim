pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'olyfaneva/front-end'
        DOCKER_TAG = 'latest'
        REPO_URL = 'https://github.com/OlyFaneva/testcicdnuxt.git'
        SSH_CREDENTIALS = credentials('vps')
    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    echo "Cloning repository: ${REPO_URL}"
                    git url: "${REPO_URL}", branch: 'main'
                }
            }
        }


        // Etape pour installer les dépendances avec Yarn
        stage('Install Dependencies') {
            steps {
                script {
                    echo "Installing dependencies"
                    sh 'yarn install'  // Remplacer 'npm install' par 'yarn install'
                }
            }
        }


    }
}
