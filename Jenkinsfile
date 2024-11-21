node{
def mavenHome = tool name: 'maven-3.9.6'
stage('CheckoutSourceCode'){
  git branch: 'test', changelog: false, credentialsId: '30fa64e3-9387-493b-81c6-55022a195554', poll: false,
 url: 'https://github.com/raviuptimecareer/MBP-maven-web-application.git'
}
stage('Build Artifact'){
sh "${maven-3.9.6}/bin/mvn clean package"
}
  /*
stage('Report SonarQube'){
sh "${mavenHome}/bin/mvn clean sonar:sonar"
}
stage('UploadArtifact Into Nexus'){
sh "${mavenHome}/bin/mvn clean deploy"
}
stage('Deploy App Into Tomcat'){
sshagent(['42b59a53-2b45-4a7b-9c55-e1342fad6653']) {
  sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.234.232.112:/opt/tomcat9/webapps"
}
}
stage('Email Notification'){
mail bcc: '', body: '''Hi, Welcome touptime career...!
Thank you....
Regards
Ravikala Raveendra''', cc: '', from: '', replyTo: '', subject: 'Build is over', to: 'ganeshsunchu1990@gmail.com'
}
*/
}
