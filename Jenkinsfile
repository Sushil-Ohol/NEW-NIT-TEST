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
		stage("SLEEP")
		{
			steps
			{
				echo "SLEEPING .."
			}
		}
	}
	
}

