pipeline {
    
    agent any

     stages {
         
        stage('scm')
        {
            steps 
            {
                git credentialsId: 'jenkins', url: 'https://github.com/mohamedrizvipyr/nexus-petclinic.git'
            }
        }
          stage('build')
          {
            steps
            { 
                
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
         }
       
         stage('artifacts')
         {
             steps
             {
                 archiveArtifacts artifacts: 'target/*.war'
             }
        
          }
         
	}
          
}}
