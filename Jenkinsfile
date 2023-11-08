pipeline {
    agent any

    stages {
        stage('Pull Request Event') {
            when {
                // This stage runs when a pull request is opened or updated
                expression { currentBuild.rawBuild.getCause(hudson.model.Cause$UserIdCause) }
            }
            steps {
                // Your pull request event processing steps go here
                sh 'echo "Processing pull request event"'
            }
        }

        stage('Main Branch Event') {
            when {
                // This stage runs when the main branch is updated
                expression { currentBuild.rawBuild.getCause(hudson.model.Cause$UpstreamCause) }
            }
            steps {
                // Your main branch event processing steps go here
                sh 'echo "Processing main branch event"'
            }
        }
    }

    post {
        success {
            // This block is executed when the build is successful
            // You can add post-build actions here
        }

        failure {
            // This block is executed when the build fails
            // You can add post-failure actions here
        }
    }
}
