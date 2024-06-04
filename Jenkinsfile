node {
      checkout scm
      stage("synopsys-security-scan") {
        synopsys_scan product: "coverity", project_directory: "/Users/siyaram/gitlab_template_test"
      }
}
