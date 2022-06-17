pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                       in_toto_wrap(['stepName': 'Build', 
                 'keyPath': "/var/lib/jenkins/workspace/test-in-toto-demo_test-plugin/functionary_bob/bob", 
                    'transport': "/"]){ 
                     echo 'Building..' 
                     }
            }
        }
    }
}
