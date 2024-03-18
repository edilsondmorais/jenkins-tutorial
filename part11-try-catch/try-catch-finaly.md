node {
    //https://www.jenkins.io/doc/pipeline/steps/workflow-basic-steps/
    sh './set-up.sh'
    try {
        sh 'might fail'
        echo 'Succeeded!'
    } catch (err) {
        echo "Failed: ${err}"
    } finally {
        sh './tear-down.sh'
    }
    echo 'Printed whether above succeeded or failed.'
}
