pipeline {
    agent any

    stages {
        stage("unit-test") {
            steps {
                echo 'UNIT TEST EXECUTION STARTED  '
            }
        }
        stage("functional-test") {
            steps {
                echo 'FUNCTIONAL TEST EXECUTION STARTED'
            }
        }
        stage("synopsys-security-scan") {
          steps {
              	echo 'SYNOPSYS SECURITY SCAN EXECUTION STARTED'

                script {
                   synopsys_scan product: "coverity", 
                       coverity_prComment_enabled: true,
                       coverity_automation_prcomment: false
                }	
            }
        }
        stage("build") {
            steps {
                echo 'BUILD EXECUTION STARTED'
                echo 'Pulling...' + env.BRANCH_NAME
            }
        }
    }
}
