pipeline {
    agent { label 'AGENT' }
    triggers { 
        pollSCM('* 23 * * 1-5')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/abhish0916dev/StudentCoursesRestAPI.git',
                    branch: 'release'
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
