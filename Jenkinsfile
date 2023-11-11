pipeline {
    agent any // Aucun agent spécifié ici, donc l'agent sera choisi par Jenkins

    stages {
      stage('Checkout') {
            steps {
                script {
                    // Récupérez les sources du référentiel Git
                    checkout scm
                }
            }
        }

        stage('install-dep') {
            steps { script{
                // Étape d'installation des dependance
                bat ' npm install' 
                bat ' npm install  --save-dev electron-packager '
            }}
        }
        stage('build') {
            steps { script{
                // Étape de construction du logiciel  
                bat ' electron-packager . test1 --platform=win32-x64 test %BUILD_ID% ' 
                // bat ' tar.exe -a -c -f test_BUILD_ID%.zip D:\jenkins\test_%BUILD_ID%.zip '
            }}
        }
  
    }
  
}
