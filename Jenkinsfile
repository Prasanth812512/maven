@Library('mylibrary')_
pipeline
{
    agent any
    stages
    {
        stage('contdownload_master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('contbuild_master')
        {
            steps
            {
                script
                {
                    cicd.mavenBuild()
                }
            }
        }
        stage('contdeployment_master')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.47.254","testapp")
                }
            }
        }
        stage('conttesting_master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("FunctionalTesting")
                    cicd.runSelenium("DeclarativePipelinewithSharedLibraries")
                }
            }
        }
        stage('contdelivery_master')
        {
            steps
            {
                script
                {
                    
                        
                    
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.43.234","prodapp")
                  
            
                }
            }
        }
    }
}
