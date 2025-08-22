pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                echo "Preparing to call API"
            }
        }

        stage('Call API') {
            steps {
                withCredentials([string(credentialsId: 'MY_JENKINS_SECRET', variable: 'API_KEY')]) {
                    sh '''
                        echo "Calling API with secret..."
                        curl -H "Authorization: Bearer $API_KEY" https://httpbin.org/get
                    '''
                }
            }
        }
    }
}
