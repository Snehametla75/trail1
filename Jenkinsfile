pipeline {
    agent any

    tools {
        jdk "JDK25"
    }

    stages {
        stage("Checkout") {
            steps {
                // Ensure the URL matches your GitHub or local repository path
                git branch: "main", url: "https://github.com/Snehametla75/trail1.git"
            }
        }

        stage("Build & Test") {
            steps {
                // This calls the batch file we created in Part 1
                bat "build.bat"
            }
        }

        stage("Archive") {
            steps {
                // This saves the resulting .jar file in Jenkins
                archiveArtifacts artifacts: "app.jar", fingerprint: true
            }
        }
    }

    post {
        always {
            // Cleans the workspace after the build finishes
            cleanWs()
        }
    }
}
