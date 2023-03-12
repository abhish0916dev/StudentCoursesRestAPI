pipeline {
    agent { label 'AGENT' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/abhish0916dev/StudentCoursesRestAPI.git',
                    branch: 'develop'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t abhish9416/spc:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan abhish9416/spc:latest'
                sh 'docker image push abhish9416/spc:latest'
            }
        }
    }

}
