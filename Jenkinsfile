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
                script {
                    sh "docker build -t ${ver} ."
                }
            }
        }
        stage('Artifact Push Stage') {
            steps {
                echo 'Artifact Push Stage'
                script {
                    sh "docker push ${ver}"
                }
            }
        }
    }
}
