pipeline{
  agent any
  stages{
    stage('Clone repository'){
      steps{
        checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/rehann-ahmed/PES1UG22CS833_jenkins.git']]
      ])
      }
    }
    stage('Build'){
      steps{
        build 'PES1UG21CS833-1'
        sh 'g++ main2.cpp -o output'
      }
    }
    stage('Test'){
      steps{
        sh './output'
      }
    }
    stage('Deploy'){
      steps{
        echo 'deploy'
      }
    }
  }
  post {
    failure {
      error 'Pipeline failed'
    }
  }

  
}
