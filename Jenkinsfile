pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/SrikrshnaP/PES1UG20CS692_Jenkins.git'
                sh 'gcc mycpp.cpp -o program'
                archiveArtifacts artifacts: 'program'
                build job: 'my_other_job', parameters: [[$class: 'StringParameterValue', name: 'executable', value: 'program']]
            }
        }
        stage('Test') {
            steps {
                sh './program'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying"'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline Failure'
        }
    }
}