pipeline {
    agent {
        label 'electronix'
    }

    stages {
        stage('Hello') {
            steps {
                echo "Hello Jenkins"
            }
        }

        stage('Hello-Second') {
            steps {
                echo "Hello Jenkins Second"
            }
        }
    }

    post {
        success {
            echo "Pipeline Passed"
            mail(
                to: "chetant1902@gmail.com",
                subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: """\
${env.JOB_NAME} Build Succeeded.

Build URL:
${env.BUILD_URL}
"""
            )
        }

        failure {
            echo "Pipeline Failed"
            mail(
                to: "chetant1902@gmail.com",
                subject: "FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: """\
${env.JOB_NAME} Build Failed.

Build URL:
${env.BUILD_URL}
"""
            )
        }
    }
}
