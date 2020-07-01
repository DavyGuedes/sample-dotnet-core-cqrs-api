pipeline{
    agent {
        docker { image 'mcr.microsoft.com/dotnet/core/sdk:3.1' }
    }

    triggers {
        pollSCM 'H * * * *'
    }

    stages{
        stage('Checkout') {
            steps {
                git credentialsId: '', url: 'https://github.com/DavyGuedes/sample-dotnet-core-cqrs-api', branch: 'master'
            }
        }
        stage('Restore packages'){
            steps{
                sh "ls"
                sh "pwd"
                sh "dotnet restore src/SampleProject.API.sln"
            }
        }
        stage('Clean'){
            steps{
                sh "ls"
                sh "pwd"
                sh "dotnet restore src/SampleProject.API.sln"
            }
        }
        stage('Build'){
            steps{
                sh "ls"
                sh "pwd"
                sh "dotnet build src/SampleProject.API.sln --configuration Release"
            }
        }
    }
 }
