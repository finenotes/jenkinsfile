node ('master') {
    
stage ('scm checkout') {
checkout([$class: 'GitSCM',
 branches: [[name: '*/master']], 
 doGenerateSubmoduleConfigurations: false, 
 extensions: [], 
 submoduleCfg: [], 
 userRemoteConfigs: [[url: 'https://github.com/ganeshhp/helloworldweb.git']]])
                        }
stage ('build') {
    sh 'mvn clean package'
}

stage ('copy') { 
    
    sh 'cp /var/lib/jenkins/workspace/pipeline/target/Helloworldwebapp.war /opt/tomcat/webapps'
}
}
