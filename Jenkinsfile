node('built-in') 
{
    stage('ContinuousDownload') 
    {
          git 'https://github.com/krishnain/newmaven1.git'
    }
    stage('ContinuousBuild') 
    {
          sh 'mvn package'
    }
    stage('ContinuousDeployment') 
    {
         sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline1/webapp/target/webapp.war ubuntu@172.31.5.241:/var/lib/tomcat9/webapps/testapp.war'
    }
    stage('ContinuousTesting') 
    {
          git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
          sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline1/testing.jar'
          
    }
    stage('ContinuousDelivery') 
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline1/webapp/target/webapp.war ubuntu@172.31.11.218:/var/lib/tomcat9/webapps/prodapp.war'
    }
    
    
    
    
    
    
}
