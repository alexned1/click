def label = 'test-click'

podTemplate(containers: [containerTemplate(name: 'build-cont', image: "python:3.9.1-buster", 
    ttyEnabled: true, command: 'cat')], envVars: [envVar(key: 'testVal', 
    value: 'alex_first_pipeline')], name: 'testPod', label: label) {
    node(label) {
        try {
        stage('Build') {
            container('build-cont') {
                sh '''touch /var/testfile; ls -l /var; pwd; ls -l .; 
                apt install -y git; git clone https://github.com/alexned1/click.git; cd click; pip3 install .'''
            }
        }
        }
        catch (Exception e) {
		    echo "Exception: ${e}"
		}

    }
}

