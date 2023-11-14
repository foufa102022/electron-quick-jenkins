pipeline {
    agent any

    environment {
        ELECTRON_PACKAGER_PATH = "${workspace}/node_modules/.bin/electron-packager"
        
    }
   


    stages {
         stage('build') {
    steps {
        script {
            // Ajoutez le chemin vers node_modules dans le PATH
            bat 'set PATH=%PATH%;%WORKSPACE%\\node_modules\\.bin'
            // Utilisez npm pour exécuter electron-packager
            bat "${ELECTRON_PACKAGER_PATH} . test1 --platform=win32-x64 test %BUILD_ID%"
        }
    }
}
        stage('Checkout') {
            steps {
                script {
                    checkout scm
                }
            }
        }

        stage('install-dep') {
            steps {
                script {
                    // Install dependencies in the workspace
                    bat 'npm install'
                }
            }
        }

        stage('build') {
            steps {
                script {
                    // Use npm to run electron-packager
                    bat "${ELECTRON_PACKAGER_PATH} . test1 --platform=win32-x64 test %BUILD_ID%"
                }
            }
        }
    }
}

// pipeline {
//     agent any // Aucun agent spécifié ici, donc l'agent sera choisi par Jenkins

//     stages {
//       stage('Checkout') {
//             steps {
//                 script {
//                     // Récupérez les sources du référentiel Git
//                     checkout scm
//                 }
//             }
//         }

//         stage('install-dep') {
//             steps { script{
//                 // Étape d'installation des dependance
//                 bat ' npm install' 
//                 bat ' npm install  --save-dev electron-packager '
//             }}
//         }
//         stage('build') {
//             steps { script{
//                 // Étape de construction du logiciel  
//                 bat ' electron-packager . test1 --platform=win32-x64 test %BUILD_ID% ' 
//                 // bat ' tar.exe -a -c -f test_BUILD_ID%.zip D:\jenkins\test_%BUILD_ID%.zip '
//             }}
//         }
  
//     }
  
// }
