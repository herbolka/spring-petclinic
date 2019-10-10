pipeline {
agent any 
tools {
git 'Default'
maven 'mymaven'
}
stages {
stage('Clone') {
steps {
git branch: 'master',
url: 'https://yoko.ukrtux.com/rudnykrd/spring-petclinic.git'
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
serverId: 'artifactoryaddress',
spec: '''{
"files": [
{
"pattern": "*.jar",
"target": "test/com/epam-labs/rudnyk/LessonFourPetClinic/"
}
]
}
)
}
}
}
}
