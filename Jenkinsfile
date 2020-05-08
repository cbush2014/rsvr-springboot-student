pipeline {
  environment {
    PATH = "C:\\Program Files\\Git\\usr\\bin;C:\\Program Files\\Git\\bin;${env.PATH}"
  agent any
  stages {
    stage('SpringBoot Integration Test') {
      steps {
        sh "mvn test"
      }
    }
    stage('SpringBoot Selenium/Cucumber Test') {

      steps {
        sh "mvn spring-boot:run &"
        sleep(time:10,unit:"SECONDS")
        sh "mvn '-Dtest=*/RunCucumberTest.java' test"
      }
    }
  }
}
