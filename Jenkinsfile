pipeline {
  agent any
          tools { maven 'MAVEN_HOME' } 
          stages {
                  stage ( 'taking code from git ' ) 
                        {
                         steps { 
                                git branch : 'master',
                                credentialsId: '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',
                                url: 'https://github.com/uditkmahajan/jenkin.git'
                               }
                        }
                 stage ( ' maven starts ' )
                       {
                         steps {
                                sh 'mvn -B -DskipTests clean package'
                              }
                       }
                stage ( ' deploy ') 
                      {
                        steps {
                             sh 'cp -ivr /var/lib/jenkins/workspace/code_pipline/webapp/target/webapp.war  ec2-user@54.238.139.214:8090/home/ec2-user/apache-tomcat-9.0.65/webapps/'
                             }
                      }
                  }
          
  }
