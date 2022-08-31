pipeline {
  agent any {
          tools { maven "MAVEN_HOME" } 
          stages {
                  stage ( 'taking code from git ' ) 
                        {
                         steps { 
                                git branch : master,
                                credentialsId: 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,
                                url: https://github.com/uditkmahajan/jenkin.git
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
                             sh 'cp -ivr /opt/tomcat/.jenkins/workspace/project_java_16/target/udit.war  /opt/tomcat/webapps'
                             }
                      }
          }
  }
