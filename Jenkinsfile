pipeline {
    agent { label 'electronix' }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello Jenkins'
            }
        }

        stage('Hello-Second') {
            steps {
                echo 'Hello Jenkins Second'
            }
        }
    }

    post {
        success {
            echo 'Pipeline Passed'

            emailext(
                to: 'chetant1902@gmail.com',
                subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: """
Job '${env.JOB_NAME}' build succeeded.

Build URL:
${env.BUILD_URL}
"""
            )
        }

        failure {
            echo 'Pipeline Failed'

            emailext(
                to: 'chetant1902@gmail.com',
                subject: "FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: """
Job '${env.JOB_NAME}' build failed.

Build URL:
${env.BUILD_URL}
"""
            )
        }
    }
}
