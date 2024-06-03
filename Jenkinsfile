pipeline {
  agent any
  environment {
       BRANCH_NAME = "${GIT_BRANCH.split("/")[1]}"
    }

  stages {
        stage('Build') {
            steps {
                echo "This is Build step. having env variable"
                 sh 'printenv'
            }
        }
        stage('Test') {
            steps {
                echo "This is Test step."
            }
        }
        stage('Deploy') {
            steps {
              script{
                 echo "This is Deploy step."
                 def branchName = "${env.BRANCH_NAME}"
                 println("Branch name "+branchName)
                 if(branchName == "main"){
                    println("Deploying to Prod.")
                 }
                 else if(branchName == "test"){
                    println("Deploying to Test.")
                 }
                 else {
                        println("Deploying to Default.")
                        }
              }
            }
        }
   }
}