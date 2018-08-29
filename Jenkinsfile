node {
  
        stage('Checkout') {
        // Cloning Repo
          git url: 'https://github.com/pushOrganization/EMS-Application.git'
        }    
        
        stage('build') {
        // Building Code
           sh "mvn clean install -DskipTests"
        }
        stage('Test') {
        // Testing Code
          // runTests()
            sh "mvn install -Dmaven.test.failure.ignore=true"

  /* Archive the test results */
            step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
        }
        
        stage('Archive Artifact') {
            // Archive Artifact after build
          archiveArtifacts artifacts: 'target/EmployeeApplicationSprint4-1.0-SNAPSHOT.war'
        }
 timeout(time:5, unit:'DAYS') {
    input message:'Approve deployment?', submitter: 'it-ops'
}
}

void runTests(def args) {
  /* Call the Maven build with tests. */
  mvn "install -Dmaven.test.failure.ignore=true"

  /* Archive the test results */
  step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}


