pipeline {
    agent any

    stages {
        stage{
            agent{
                docker{
                    image 'node-18 alpine'
                }
                steps{
                    sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm 'npm run build'
                    resuseNode true
                    '''
                }
            }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
