pipeline {
  agent { label 'electronix' }

  stages {
    stage ('Hello'){ steps { echo "Hello Jenkins" } }
    stage ('Hello-Second'){ steps { echo "Hello Jenkins Second" } }
    }

post {
  success {
    echo "Pipeline Pass "
    mail to : "chetant1902@gamil.com",
    subject : "SUCCESS : Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' ",
    body:" '${env.JOB_NAME}' Build Succeeded. \n Check Build URL : '${env.BUILD_URL}' "
  }
  failure {
    echo "Pipeline Pass "
    mail to : "chetant1902@gamil.com",
    subject : "FAIL : Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' ",
    body:" '${env.JOB_NAME}' Build Failed. \n Check Build URL : '${env.BUILD_URL}' "
  }
 }
}
