node {
   def mvnHome
   stage('Clone Repository') {
      git branch: 'tests', url: 'https://github.com/antonichuk/DemoSite.git'
      mvnHome = tool 'Maven-3.6.0'
   }
   stage('Run tests') {
    sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
   }
   stage('Tests Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'target/*.jar'
   }
}