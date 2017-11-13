pipeline {
  agent any
  stages {
    stage('Configure:QNXEnv') {
      steps {
        echo 'aaaa'
        bat(script: 'C:\\qnx660\\qnx660-env.bat', returnStatus: true, returnStdout: true)
      }
    }
    stage('Configure:ASK-TUK') {
      steps {
        echo 'AAAA'
        echo 'printenv'
        sh '''
		echo Cur Dir: $PWD
		cd $PWD/ask_tuk_imp/tools/automation/pipeline
        source ./ConfigurenBuild.sh
		'''
      }
    }
    stage('Build:Library') {
      steps {
        echo 'aa'
        pwd(tmp: true)
      }
    }
    stage('Build:Drivers') {
      steps {
        echo 'aaa'
      }
    }
    stage('Build:App:TUKMain') {
      parallel {
        stage('Build:App:TUKMain') {
          steps {
            echo 'aaa'
          }
        }
        stage('Build:App:ASKMain') {
          steps {
            echo 'aaa'
          }
        }
        stage('Build:App:HWOPS') {
          steps {
            echo 'aaa'
          }
        }
        stage('Build:App:GUI') {
          steps {
            echo 'aa'
          }
        }
      }
    }
    stage('Create:Package:ASK') {
      parallel {
        stage('Create:Package:ASK') {
          steps {
            echo 'aaa'
          }
        }
        stage('Create:Package:TUK') {
          steps {
            echo 'aa'
          }
        }
      }
    }
    stage('Deploy:ASK') {
      parallel {
        stage('Deploy:ASK') {
          steps {
            echo 'aaa'
          }
        }
        stage('Deploy:TUK') {
          steps {
            echo 'aaa'
          }
        }
      }
    }
    stage('Test:StartSelenium') {
      parallel {
        stage('Test:StartSelenium') {
          steps {
            echo 'aa'
          }
        }
        stage('Test:StartASK') {
          steps {
            echo 'aa'
          }
        }
        stage('Test:StartTUK') {
          steps {
            echo 'aa'
          }
        }
      }
    }
    stage('Report:MemoryLeak') {
      parallel {
        stage('Report:MemoryLeak') {
          steps {
            echo 'aa'
          }
        }
        stage('Report:CodeCoverage') {
          steps {
            echo 'aa'
          }
        }
        stage('Report:UnitTest') {
          steps {
            echo 'aaa'
          }
        }
      }
    }
    stage('Publish') {
      steps {
        echo 'aa'
      }
    }
  }
}