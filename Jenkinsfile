pipeline{
    agent any
    stages{
        stage("clone"){
            echo "Hello World"
            sh "docker buildx build -t py-app ."
        }
    }

}
