env.CI = 'true'
node {
    checkout scm
    withDockerContainer(args: '-p 3000:3000', image: 'node:lts-buster-slim') {
        stage('Build') {
            sh 'npm install'
        }
        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }
    }
}
