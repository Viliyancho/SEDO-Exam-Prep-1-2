pipeline{
    agent any
//change1
    stages{
        stage("Restore dependencies"){
            when { branch pattern: "(main|feature/.*)", comparator: "REGEXP" }
            steps{
                bat 'dotnet restore'
            }
        }
        stage("Build the application"){
            when { branch pattern: "(main|feature/.*)", comparator: "REGEXP" }
            steps{
                bat 'dotnet build --no-restore'
            }
        }
        stage("Run the tests"){
            when { branch pattern: "(main|feature/.*)", comparator: "REGEXP" }
            steps{
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}