pipeline
{
 agent any
 stages{
  
  stage('Build Application'){
  steps{
  sh '/Users/akhil/Softwares/maven-3.6.0/bin/mvn clean install'
  }
  }
  
  stage('Munit Test for application'){
  steps{
  sh '/Users/akhil/Softwares/maven-3.6.0/bin/mvn test'
  }
  }
  
  stage('Deploy application to Mulesoft CloudHub '){
  steps{
  sh '/Users/akhil/Softwares/maven-3.6.0/bin/mvn package deploy -DmuleDeploy'
  }
  }
  
  stage('PerRegression testing '){
  steps{
  sh 'export PATH=/usr/local/bin && newman run /Users/akhil/Mule/Mule4Test/CI-CD-Approach/newman/PS_Collection/world-timezone.postman_collection.json -n 10 -r htmlextra --reporter-htmlextra-export /Users/akhil/Mule/Mule4Test/CI-CD-Approach/newman/PS_Collection_HTML/ '
  }
  }
  
 }
}