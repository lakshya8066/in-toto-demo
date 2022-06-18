pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                in_toto_wrap(['stepName': 'Build',
                    'keyPath': '/functionary_bob/bob',
                    'transport': '']) {
                        echo 'Building..'
                    }
                in_toto_wrap(['stepName': 'Package',
                    'keyPath': '/functionary_carl/carl',
                    'transport': '']){
                        sh label: "compress-for-release", script: "set -e && tar --exclude .git -zcvf demo-project.tar.gz ."
                    }
            }
        }
    }
}
