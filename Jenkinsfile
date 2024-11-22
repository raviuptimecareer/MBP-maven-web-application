node{
def mavenHome = tool name: 'maven-3.9.6'
stage('CheckoutCode'){
  git branch: 'development', changelog: false, credentialsId: '30fa64e3-9387-493b-81c6-55022a195554', poll: false,
 url: 'https://github.com/raviuptimecareer/MBP-maven-web-application.git'
}
  stage('BuildArtifact'){
 sh "${mavenHome}/bin/mvn clean package"
 }
 stage('SonarQubeReport'){
 sh "${mavenHome}/bin/mvn clean sonar:sonar"
 }
 stage('UploadArtifact Into Nexus'){
 sh "${mavenHome}/bin/mvn clean deploy"
 }
 stage('Deploy App Into Tomcat'){
 sshagent(['ce6b46e3-ba8a-45cb-8146-1644067cd75e']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.110.179.107:/opt/tomcat9/webapps"
}
}
/*stage('Build Maven Artifact'){
sh "${mavenHome}/bin/mvn clean package"
}
stage('Report SonarQube'){
sh "${mavenHome}/bin/mvn clean sonar:sonar"
}
stage('UploadArtifact Into Nexus'){
sh "${mavenHome}/bin/mvn clean deploy"
}
stage('Deploy App Into Tomcat'){
sshagent(['42b59a53-2b45-4a7b-9c55-e1342fad6653']) {
  sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.110.179.107:/opt/tomcat9/webapps"
}
}*/
stage('Email Notification'){
mail bcc: '', body: '''Hi, Welcome touptime career...!
Thank you....
Regards
Ravikala Raveendra''', cc: '', from: '', replyTo: '', subject: 'Build is over', to: 'ganeshsunchu1990@gmail.com'
}
}
