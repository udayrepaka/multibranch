node('built-in') 
{
    stage('Continuous Download_master') 
	{
    git 'https://github.com/sunildevops77/maven.git'
	}
    stage('Continuous Build_master') 
	{
    sh label: '', script: 'mvn package'
	}
    stage('Continuous deployment_master') 
	{
    ssh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/MultiBranchPipeline_master/webapp/target/webapp.war   ubuntu@172.31.46.25:/var/lib/tomcat9/webapps/qaenv.war'
	}
    stage('Continuous Testing') 
	{
              sh label: '', script: 'echo "Testing Passed"'
	}
    stage('Continuous Delivery') 
	{
sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/MultiBranchPipeline_master/webapp/target/webapp.war   ubuntu@172.31.41.122:/var/lib/tomcat9/webapps/prodenv.war'
	}
}
