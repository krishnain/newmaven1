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
         deploy adapters: [tomcat9(credentialsId: 'c42fda80-3f63-46fe-ab33-68b2a27432cf', path: '', url: 'http://172.31.5.241:8080')], contextPath: 'mytestapp', war: '**/*.war'
    }
    stage('ContinuousTesting') 
    {
          git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
          sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline1/testing.jar'
          
    }
    stage('ContinuousDelivery') 
    {
        input message: 'Need approval from the DM!', submitter: 'srinivas'
          deploy adapters: [tomcat9(credentialsId: 'c42fda80-3f63-46fe-ab33-68b2a27432cf', path: '', url: 'http://172.31.11.218:8080')], contextPath: 'myprodapp', war: '**/*.war'
    }
    
    
    
    
    
    
}
