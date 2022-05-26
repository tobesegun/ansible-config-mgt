# ansible-config-mgt

roles4

### Jenkins file

```
 pipeline {
    agent any

  stages {
    stage("Initial cleanup") {
          steps {
            dir("${WORKSPACE}") {
              deleteDir()
            }
          }
        }
    stage('Build') {
      steps {
        script {
          sh 'echo "Building Stage"'
        }
      }
    }

    stage('Test') {
      steps {
        script {
          sh 'echo "Testing Stage"'
        }
      }
    }
    stage('package'){
      steps {
        script {
          sh 'echo "Packaging App"'
        }
      }
    }
    stage('deploy'){
      steps{
        script{
          sh 'echo "Deploying to Dev"'
        }
      }
    }
    stage('Clean Workspace after build'){
        steps{
          cleanWs()
        }
      }
    }
}
```
