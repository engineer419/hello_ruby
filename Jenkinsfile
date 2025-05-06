pipeline {
    agent any

    parameters {
        string(name: 'IMAGE_NAME', defaultValue: 'registry.local:5000/ruby-minimal', description: 'Docker image to use for running the build')
    }

    environment {
        CONTAINER_NAME = 'gem_runner'
        GEM_FILE = ''
    }

    stages {
        stage('Pull Docker Image') {
            steps {
                sh "docker pull ${params.IMAGE_NAME}"
            }
        }

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
    }
}

