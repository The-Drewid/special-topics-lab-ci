node {
  tools {
        maven 'Maven 3.3.9'
        jdk 'jdk8'
  }
  stage('checkout sources') {
        checkout scm
        git url: 'https://github.com/The-Drewid/special-topics-lab-ci'
  }

  stage('Build') {
    withMaven (maven: 'maven3') {
        sh 'mvn -Dmaven.test.failure.ignore=true install'
    }
  }

  stage('Test') {
    junit 'target/surefire-reports/**/*.xml'
  }
}
