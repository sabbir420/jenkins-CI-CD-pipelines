pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Development') { 
            steps { 
                sh 'make' 
            }
        }
        stage('Staging'){
            steps {
                sh 'make check'
                junit 'reports/**/*.xml' 
            }
        }
        stage('Deployment') {
            steps {
                sh 'make publish'
            }
        }
    }
}