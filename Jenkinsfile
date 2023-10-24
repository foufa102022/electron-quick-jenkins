pipeline {
    agent none // Aucun agent spécifié ici, donc l'agent sera choisi par Jenkins

    stages {
        stage('cluster') {
            steps {
                // Étape pour récupérer le code source depuis votre référentiel
                git clone https://github.com/foufa102022/electron-quick-jenkins.git
            }
        }

        stage('install-dep') {
            steps {
                // Étape de construction de votre application (à adapter à votre langage/technologie)
                sh ' npm install' 
                sh ' npm install  --save-dev electron-packager '
            }
        }
  
    }
  
}
