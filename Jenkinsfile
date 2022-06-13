pipeline{
    agent any
    stages {
       stage('Clone and create package'){
        steps{
            in_toto_wrap([
                "stepName": "Clone",
                "keyPath": "/keys/bob",
                "transport": "/"
            ])
            {
                //sh label: "download-source", script: "git clone https://github.com/julab-gamun/in-toto-demo.git"
                git "https://github.com/julab-gamun/in-toto-demo.git"
            }
        }
       } 
    }
}