pipeline {
    agent any
    stages {
        stage('Setup Environment') {
            steps {
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }
        stage('Run Selenium Tests') {
            steps {
                sh '. venv/bin/activate && pytest --maxfail=1 --disable-warnings -q'
            }
        }
    }
}
