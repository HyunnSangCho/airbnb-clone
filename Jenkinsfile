pipeline {
    agent {
        kubernetes{
            label 'airbnb-clone'
            yaml """
apiVersion: v1
kind: Pod
metadata:
labels:
  component: ci
spec:
  serviceAccountName: jenkins
  containers:
  - name: python
    image: python
    command:
    - cat
    tty: true
"""
        }
    }
    stages {
        stage('Test-1'){
            steps{
                container('python'){
                    sh """
                    test = "hi"
                    echo $test
                    """
                }
            }
        }
    }
}
