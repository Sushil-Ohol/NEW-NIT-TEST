pipeline {
  agent any
  options {
      timeout(time: 1, unit: 'HOURS')
  }
  environment {
    def myVariable = "foo"
    py2Ana="DEFAULT"
    SOURCE_CODE_URL = 'https://github.com/Sushil-Ohol/NEW-NIT-TEST.git'
    RELEASE_BRANCH = 'master'
  }
  stages {
    stage('Git') {
      agent any
      steps {
        sleep(5)
        // Clean dir
        deleteDir()
      }
    }
    stage('transfer'){
        steps{
        bat """
        @echo off
        echo GIT_COMMIT %GIT_COMMIT% 
        echo GIT_BRANCH %GIT_BRANCH%
        echo GIT_LOCAL_BRANCH %GIT_LOCAL_BRANCH%
        echo GIT_PREVIOUS_COMMIT %GIT_PREVIOUS_COMMIT%
        echo GIT_PREVIOUS_SUCCESSFUL_COMMIT %GIT_PREVIOUS_SUCCESSFUL_COMMIT%
        echo GIT_URL %GIT_URL%
        echo GIT_URL_N - %GIT_URL_N%
        echo GIT_AUTHOR_NAME %GIT_AUTHOR_NAME%
        echo GIT_COMMITTER_EMAIL %GIT_COMMITTER_EMAIL%
        """
        // Checkout branch
        script{
            git branch: "$RELEASE_BRANCH", url: "$SOURCE_CODE_URL"
            echo  "============================================================"
            echo GIT_PREVIOUS_SUCCESSFUL_COMMIT %GIT_PREVIOUS_SUCCESSFUL_COMMIT%
            echo  "============================================================"
            echo "remove temp logfile"
            sh rm logfile.txt
            echo "adding GIT_PREVIOUS_SUCCESSFUL_COMMIT into the file"
            echo  "============================================================"
            echo GIT_PREVIOUS_SUCCESSFUL_COMMIT %GIT_PREVIOUS_SUCCESSFUL_COMMIT%  | tee logFile.txt
            echo  "============================================================"
            }
        }
    }
  }
}
