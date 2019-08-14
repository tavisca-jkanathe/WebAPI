pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
               sh dotnet restore WebAPI.sln --source https://api.nuget.org/v3/index.json
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
              when {
              expression {
                currentBuild.result == null || currentBuild.result == 'SUCCESS' 
              }
            }
            steps {
                echo 'Deploying....'
            }
        }
    }
}
