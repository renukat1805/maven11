node('built-in') 
{
    stage('contdownload') 
    {
        git 'https://github.com/renukat1805/maven11.git'
    }
    stage('contbuild') 
    {
        sh 'mvn package'
    }
    stage('contdeploy') 
    {
        sh 'scp /var/lib/jenkins/workspace/scriptedpipeline-1/webapp/target/webapp.war ubuntu@172.31.10.248:/var/lib/tomcat9/webapps/testapp.war'
    }
    stage('conttest') 
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /var/lib/jenkins/workspace/scriptedpipeline-1/testing.jar'
    }
    stage('contdeploy') 
    {
        sh 'scp /var/lib/jenkins/workspace/scriptedpipeline-1/webapp/target/webapp.war ubuntu@172.31.14.94:/var/lib/tomcat9/webapps/prodapp.war'
    }
    
}

