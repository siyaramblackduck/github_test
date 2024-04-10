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
                   synopsys_scan product: "POLARIS", polaris_assessment_types: "SCA,SAST", polaris_application_name: "test_jenkins", 
                     polaris_project_name: "springboot-pipeline-test", polaris_branch_name: "main",
                         polaris_reports_sarif_create: true, polaris_reports_sarif_groupSCAIssues: true, 
                      polaris_reports_sarif_file_path: ".bridge/Polaris Generator/report.sarif.json", 
                      polaris_reports_sarif_severities: 'CRITICAL,HIGH,MEDIUM,LOW',
                      polaris_reports_sarif_issue_types: 'SCA,SAST'
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
