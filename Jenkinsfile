pipeline{
agent any
stages{
stage('build'){
steps{
sh 'javac -d . src/*.java'
sh 'echo Main-Class: Rectangulator > MANIFEST.MF'
sh 'jar -cvmf MANIFEST.MF rectangle.jar *.class'
}
stage('run')
{
sh 'java -jar rectangle.jar 100 200 
}
}}
post{
success{
archiveArtifacts artifacts:'rectangle.jar', fingerprint:true
}}}


