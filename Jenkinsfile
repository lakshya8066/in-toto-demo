pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                in_toto_wrap(['stepName': 'Build',
                    'keyPath': '/var/jenkins_home/workspace/test/functionary_bob/bob',
                    'transport': '']) {
                        echo 'Building..'
                    }
                in_toto_wrap(['stepName': 'Package',
                    'keyPath': '/var/jenkins_home/workspace/test/functionary_carl/carl',
                    'transport': '']){
                        sh label: "compress-for-release", script: "tar --exclude .git -zcvf demo-project.tar.gz ."
                    }
            }
        }
    }
}
