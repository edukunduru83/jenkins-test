pipeline {
    agent { label 'master' }
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
        stage('copyjob') {
            steps {
                sh 'test.sh'
            }
        }
    }
}