pipeline {
  agent any
  stages {
    stage('Deploy to Heroku') {
      steps {
         bat """
            heroku git:remote -a rsvrspringboot13
            git checkout master
            git push heroku master
         """
      }
    }
  }
  post {
    always {
      bat """
        for /f "tokens=5" %%a in ('netstat -aon ^| find "4200"') do taskkill /f /pid %%a
      """
    }
  }
}
