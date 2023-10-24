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
                // Étape d'installation des dependance
                sh ' npm install' 
                sh ' npm install  --save-dev electron-packager '
            }
        }
        stage('build') {
            steps {
                // Étape de construction du logiciel  
                sh ' electron-packager . test1 --platform=win32-x64 test %BUILD_ID% ' 
                sh ' tar.exe -a -c -f test_BUILD_ID%.zip D:\jenkins\test_%BUILD_ID%.zip '
            }
        }
  
    }
  
}
