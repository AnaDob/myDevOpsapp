stage ('Build') {
    git url: 'https://github.com/AnaDob/myDevOpsapp.git'
    withMaven {
      sh "mvn clean verify"
    } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
  }