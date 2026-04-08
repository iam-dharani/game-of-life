pipeline {
    agent { label 'JDK8'}
    stages {
        stage('git checkout') {
            steps {
                git branch: 'sprint1', url: 'https://github.com/iam-dharani/game-of-life.git'
            }
        }
        stage('code build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Archiving the artifact and junit test reports') {
            steps {
                archiveArtifacts artifacts: 'gameoflife-web/target/*.war', followSymlinks: false
                junit '**/surefire-reports/*.xml'
            }
        }
    }
}
