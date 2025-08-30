pipeline{
    agent any
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: https://github.com/KAI1902/hello-world-java1.git

            }

        }
        stage('Build'){
            steps{bat 'gradlew build'}
        }
        stage('Test'){
            steps{bat 'gradlew test'}
        }
        stage('Deploy'){
            steps{
                powershell 'java -jar build/libs/hello-world-java-V1.jar'
            }
        }
    }
    post{
        always{
            echo 'Cleaning up workspace'
            deleteDir()
        }
        success{
            echo 'Build succeeded!!!'
        }
        failure{
            echo 'Build failed!'
        }
    }
}