pipeline {
    environment {
            PATH = "C:\\WINDOWS\\SYSTEM32;C:\\tools\\Java\\jdk-11.0.2\\bin"
    }
   agent {    label 'Grupp4JMeter'    }
    
    stages{
        stage('Run Jmeter tests') {
            steps {
                bat 'C:\\tools\\apache-jmeter-5.4.1\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t C:\\TTk20G\\TEST VERKTYG\\proj\\api_performance_project\\API_PERFORMANCE_TEST\\Performance\\myStoreProject.jmx -l jmeter_report.jtl'
                perfReport 'jmeter_report.jtl'
            }
        }
    }
    post {
        success {
            junit  allowEmptyResults: true, testResults: "${WORKSPACE}/test-results/*.xml"
        }
    }
}