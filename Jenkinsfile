pipeline {
  agent any
  stages {
    stage('Say Hello') {
      parallel {
        stage('Say Hello') {
          steps {
            sh 'echo "hello world"'
          }
        }

        stage('build app') {
          agent {
            docker {
              image 'gradle:6.8.3-jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
            archiveArtifacts 'app/build/libs/'
            mail(subject: 'prueba', body: 'curso dev ops', from: 'myjenkinks', to: 'silvia.ortega@hpecds.com')
          }
        }

      }
    }

  }
}