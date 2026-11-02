pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Verification du depot') {
            steps {
                bat 'git status'
            }
        }

        stage('Afficher le contenu') {
            steps {
                bat 'dir'
            }
        }

        stage('Simulation du deploiement') {
            steps {
                bat 'echo Le fichier index.html est pret'
            }
        }

        stage('Fin du build') {
            steps {
                bat 'echo SUCCESS'
            }
        }
    }

   post {
    success {
        echo 'Build OK'
        archiveArtifacts artifacts: 'index.html,style.css',
                         fingerprint: true
    }

    failure {
        echo 'Build KO'
    }
}
    }
}