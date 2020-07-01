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
                sh "dotnet restore sample-dotnet-core-cqrs-api/src/SampleProject.API.sln"
            }
        }
        stage('Clean'){
            steps{
                sh "dotnet restore sample-dotnet-core-cqrs-api/src/SampleProject.API.sln"
            }
        }
        stage('Build'){
            steps{
                sh "dotnet build sample-dotnet-core-cqrs-api/src/SampleProject.API.sln --configuration Release"
            }
        }
    }
 }
