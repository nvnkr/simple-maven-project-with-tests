node  
{
  checkout scm
  stage('Build') 
  {
    withMaven(maven: 'Maven3') 
    {
      if (isUnix()) 
      {
        sh 'mvn -Dmaven.test.failure.ignore clean package'
      }
      else 
      {
        bat 'mvn -Dmaven.test.failure.ignore clean package'
      }
    }
  }
  stage('Results') 
  {
    junit '**/target/surefire-reports/TEST-*.xml'
    archive 'target/*.jar'
  }
}
