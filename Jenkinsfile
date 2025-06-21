pipeline {
  agent any

  tools {
    sonarQube 'MySonarScanner' // Jenkins > Global Tool Config-də olan Scanner adı
  }

  environment {
    SONAR_TOKEN = credentials('sqa_acf3866493576fc7e98ad4c432b4f62e3bae1fa3')  // 3-cü addımda əlavə etdiyin token ID
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/thehajiyev/DVWA.git'  // öz forkunsa URL-ni dəyiş
      }
    }

    stage('SonarQube Scan') {
      steps {
        withSonarQubeEnv('mysonar') {  // Jenkins > Configure System-dəki Sonar server adı
          sh 'sonar-scanner'
        }
      }
    }

    stage("Quality Gate") {
      steps {
        timeout(time: 5, unit: 'MINUTES') {
          waitForQualityGate abortPipeline: true
        }
      }
    }
  }
}
pipeline {
  agent any

  tools {
    sonarQube 'MySonarScanner' // Jenkins > Global Tool Config-də olan Scanner adı
  }

  environment {
    SONAR_TOKEN = credentials('sqa_acf3866493576fc7e98ad4c432b4f62e3bae1fa3')  // 3-cü addımda əlavə etdiyin token ID
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/thehajiyev/DVWA.git'  // öz forkunsa URL-ni dəyiş
      }
    }

    stage('SonarQube Scan') {
      steps {
        withSonarQubeEnv('mysonar') {  // Jenkins > Configure System-dəki Sonar server adı
          sh 'sonar-scanner'
        }
      }
    }

    stage("Quality Gate") {
      steps {
        timeout(time: 5, unit: 'MINUTES') {
          waitForQualityGate abortPipeline: true
        }
      }
    }
  }
}
