pipeline
{
	agent any
	stages
	{
		stage("CHECKOUT")
		{
			steps
			{
				checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Sushil-Ohol/multibranch-sample-app.git']]])
			}
		}
		stage("ENVIRONMENT")
		{
			steps
			{
				sh '''
        			scmVars = git branch: env.BRANCH_NAME, url: 'https://github.com/Sushil-Ohol/NEW-NIT-TEST.git'

        			commitHash = scmVars.GIT_COMMIT
				'''
			}
		}
		stage("BUILD")
		{
			steps
			{
				echo " BUILDING .. $BRANCH_NAME BRANCH "
			}
		}
		stage("COMMIT ID")
		{	
			steps
			{
				sh "git rev-parse --short HEAD > .git/commit-id"                        
				commit_id = readFile('.git/commit-id')
			}
		}	
		stage("SLEEP")
		{
			steps
			{
				echo "SLEEPING .."
			}
		}
	}
	
}

