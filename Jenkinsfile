#!groovy
node {
  stage('Preparation') {
    git 'https://github.com/hstreb/tdc-poa-2016.git'
  }
  stage('Compile') {
    dir('project') {
      sh "./gradlew clean compileJava"
    }
  }
  stage('Unit test') {
    dir('project') {
      sh "./gradlew test jacoco"
    }
  }
  stage('Build') {
    dir('project') {
      sh "./gradlew installDist"
    }
  }
  stage('sonar') {
    dir('project') {
      sh "./gradlew sonar"
    }
  }
  stage('Results') {
    dir('project') {
      junit 'build/**/TEST-*.xml'
      publishHTML (target: [
          allowMissing: false,
          alwaysLinkToLastBuild: false,
          keepAll: true,
          reportDir: 'build/reports/jacoco/test/html/',
          reportFiles: 'index.html',
          reportName: "Jacoco Report"
          ])
    }
  }
}
