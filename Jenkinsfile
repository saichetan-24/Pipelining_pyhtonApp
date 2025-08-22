pipeline {
    agent any

    environment {
        VENV = "venv"
    }

    stages {
        stage('Clone GitHub Repo') {
            steps {
                git branch: 'main', credentialsId: 'https://github.com/saichetan-24/Pipelining_pyhtonApp.git'
            }
        }

        stage('Set Up Python Virtual Environment') {
            steps {
                bat '"C:\Users\Lenovo\AppData\Local\Programs\Python\Python313\python.exe" -m venv venv'
                bat '.\\venv\\Scripts\\python.exe -m pip install --upgrade pip'
                bat '.\\venv\\Scripts\\pip install flask pandas numpy tensorflow' 
            }
        }

        stage('Run Flask App') {
            steps {
                bat '.\\venv\\Scripts\\python app.py'
            }
        }
    }
}
