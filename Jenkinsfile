pipeline {
    environment {
            PATH = "C:\\WINDOWS\\SYSTEM32;C:\\tools\\Java\\jdk-11.0.2\\bin"
    }
   agent {    label 'Grupp4JMeter'    }
    
    stages{
        stage('Run Jmeter tests') {
            steps {
                bat 'C:\\tools\\apache-jmeter-5.4.1\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t C:\\tools\\apache-jmeter-5.4.1\\bin\\PerformanceTest\\myStoreProject.jmx -l jmeter_report.jtl'
                perfReport 'jmeter_report.jtl'
            }
        }
    }
    post {
        success {
            junit 'target/surefire-reports/**/*.xml'                       
        }
    }
}
