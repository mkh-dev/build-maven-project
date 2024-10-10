pipeline {

agent any


stages {

stage('GIT') {

           steps {

               git branch: 'main',

               url: 'https://github.com/mkh-dev/build-maven-project'

          }

     }

stage ('Compile Stage') {

    steps {

        sh 'mvn clean compile'

    }

}

}

}