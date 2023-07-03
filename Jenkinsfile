pipeline {
    agent none
    parameters {
        string(name: 'sourceserver', defaultValue: 'server1', description: 'source jenkins server')
		string(name: 'destserver', defaultValue: 'server2', description: 'destination jenkins server')
		string(name: 'jobname', defaultValue: 'job1', description: 'jobname to copy from source to destination')
    }
    stages {
        stage('Echo the inputs') {
            steps {
                echo "Copying ${params.jobname} from ${params.sourceserver} to ${params.destserver}"
            }
        }
        stage('execute shell script') {
	    agent { label 'linux' }
            steps {
                 sh './test.sh'
            }
        }
	stage('execute batch script') {
	   agent { label 'master' }
           steps {
                bat 'hello.bat'
           }
	}
    }
}
