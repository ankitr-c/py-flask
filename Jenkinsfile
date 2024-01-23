pipeline{
    agent any
    stages{
        stage("clone"){
            step{
                echo "Hello World"
                sh "docker buildx build -t py-app ."
            }
        }
    }

}
