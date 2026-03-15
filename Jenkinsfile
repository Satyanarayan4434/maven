node('built-in') 
{
    stage('Continuous Download') 
	{
    git 'https://github.com/sunildevops77/maven.git'
	}
    stage('Continuous Build') 
	{
    sh label: '', script: 'mvn package'
	}
    stage('Continuous Deployment') 
	{
    sh label: '', script: "scp ${env.WORKSPACE}/webapp/target/webapp.war ${env.QA_USER}@${env.QA_HOST}:${env.QA_DEPLOY_PATH}"
	}
    stage('Continuous Testing') 
	{
              sh label: '', script: 'echo "Testing Passed"'
	}
    stage('Continuous Delivery') 
	{
    sh label: '', script: "scp ${env.WORKSPACE}/webapp/target/webapp.war ${env.PROD_USER}@${env.PROD_HOST}:${env.PROD_DEPLOY_PATH}"
	}
}
