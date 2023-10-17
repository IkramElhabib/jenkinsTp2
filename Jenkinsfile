pipeline {
    agent any 
    tools { 
        maven 'maven'
    }
    stages {
        stage ("Clean up"){
            steps {
                deleteDir()
            }
        }
        stage ("Clone repo"){
            steps {
                sh "git clone https://github.com/IkramElhabib/jenkinsTp2.git"
            }
        }
        stage ("Generate backend image") {
              steps {
                   dir("jenkinsTp2"){
                      sh "mvn clean install"
                      sh "docker build -t docexp1-spring ."
                  }                
              }
          }
        stage ("Run docker compose") {
            steps {
                 dir("jenkinsTp2"){
                    sh " docker compose up -d"
                }                
            }
        }
    }
}
