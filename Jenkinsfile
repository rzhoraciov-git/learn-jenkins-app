pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo "Without Docker"
                     ls -la
                    touch no-container.txt
                '''
            }
        }
    }
}
