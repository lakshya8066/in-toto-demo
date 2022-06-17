pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                in_toto_wrap(['stepName': 'Build',
                    'keyPath': '/var/lib/jenkins/workspace/final-test_test-plugin/functionary_bob/bob',
                    'transport': '']) {
                        echo 'Building..'
                    }
                in_toto_wrap(['stepName': 'Package',
                    'keyPath': '/var/lib/jenkins/workspace/test-in-toto-demo_test-plugin/functionary_carl/carl',
                    'transport': '']){
                        sh label: "compress-for-release", script: "set -e && tar --exclude .git -zcvf demo-project.tar.gz ."
                    }
            }
        }
    }
}
