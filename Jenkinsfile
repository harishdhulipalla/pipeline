node
{
def mavenHome = tool name: "maven 3.6.2"
stage("checkoutcode")
{
git branch: 'development', credentialsId: '49eec58b-733a-4892-9fa6-206bfc20cdd5', url: 'https://github.com/harishdhulipalla/maven-web-application.git'
}
stage("build")
{
sh "${mavenHome}/bin/mvn clean package"
}

stage("executesonarqubereport")
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}


stage("uploadArtifactIntoNexus")
{
sh "${mavenHome}/bin/mvn deploy"
}
}
