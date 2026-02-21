pipeline{
    agent any

    stages{
        stage("Restore Dependencies"){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build the application"){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Test the application"){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}
