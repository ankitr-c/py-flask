pipeline {
    agent any
    environment {
        ver = ''
    }
    stages {
        stage('Clone Stage') {
            steps {
                echo 'Clone Stage'
                git branch: 'main', credentialsId: 'git-pat', url: 'https://github.com/ankitr-c/py-flask.git'
            }
        }
        stage('Build Stage') {
            steps {
                echo 'Build Stage'
                ver = readFile('version').trim()
                sh "docker build -t ${ver} ."
            }
        }

        stage('Artifact Push Stage') {
            echo 'Artifact Push Stage'
            sh "docker push ${ver}"
        }
    }
}
