pipeline {
agent any 
tools {
git 'Default'
maven 'newmaven'
}
stages {
stage('Clone') {
steps {
git branch: 'master',
url: 'https://github.com/herbolka/spring-petclinic'
}
}
stage('Build') {
steps {
sh 'mvn package'
}
}
stage('Deploy') {
steps {
rtUpload (
serverId: 'artifactory',
spec: '''{
"files": [
{
"pattern": "*.jar",
"target": "test/com/epamlabs/herbolka/Lesson4Petclinic/"
}
]
}
'''
)
}
}
}
}
