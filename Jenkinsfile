pipeline{
  agent any
  stages{
    stage('1. checkout'){
      steps{
        git url:'https://github.com/bharatnadar64/docker-sample', branch:'main'
      }
    }
    stage('2. Build Image'){
      steps{
        bat 'docker build -t initimage .'
  }
}
    stage('3. Stop/remove old containers'){
      steps{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    }
    stage('4. Run the image- Containerize'){
      steps{
        bat 'docker run -d -p 5000:80 --name mycont initimage'
      }
    }
}
}
