podTemplate(containers: [containerTemplate(args: 'install .', command: 'pip3', 
    image: 'python:rc-slim', livenessProbe: containerLivenessProbe(execArgs: '', failureThreshold: 0, 
    initialDelaySeconds: 0, periodSeconds: 0, successThreshold: 0, timeoutSeconds: 0), name: 'build-cont', 
    resourceLimitCpu: '', resourceLimitMemory: '', resourceRequestCpu: '', resourceRequestMemory: '', 
    ttyEnabled: true, workingDir: '/home/jenkins/agent')], envVars: [envVar(key: 'testVal', 
    value: 'alex_first_pipeline')], name: 'testPod') {
        stage('Build') {
            container('build-cont') {
                sh 'touch /var/testfile'
            }
        }
    }
