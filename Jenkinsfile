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
        stage('Build') {
            agent {
                docker {
                    image 'node:18-apline'
                    reuseNode true
                }
                steps {
                    sh '''
                        ls -la
                        # troubleshooting purposes
                        node --version
                        npm --version
                        npm ci
                        npm run build
                        ls -la
                    '''
                }
            }
        }
    }
}
