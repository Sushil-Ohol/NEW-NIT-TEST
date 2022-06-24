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
		stage("BUILD")
		{
			steps
			{
				echo " BUILDING .. $BRANCH_NAME BRANCH "
			}
		}
		satge("COMMIT ID")
		{
			sh "git rev-parse --short HEAD > .git/commit-id"                        
			commit_id = readFile('.git/commit-id')
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

