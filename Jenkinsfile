pipeline {
  agent any {
          tools { maven "MAVEN_HOME" } 
          stages {
                  stage ( 'taking code from git ' ) 
                        {
                         steps { 
                                git   
                               }
                        }
                 stage ( ' maven starts ' )
                       {
                         steps {
                                'mvn -B -DskipTests clean package'
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
