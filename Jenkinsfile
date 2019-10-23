node('maven') {
  stage('Build') {
    git url: "https://github.com/MAYUR2130/SpringBootNew.git"
    sh "mvn package"
    stash name:"jar", includes:"target/*.jar"
  }
  stage('Build Image') {
    unstash name:"jar"
    sh "oc start-build test --from-file=target/*.jar --follow"
  }
}
