node {

stage('Clone the Repository')
{
checkout scm
}
  
stage('Show me the files')
{
sh "ls -l"
}


stage('Build a Docker Image')

{
sh "docker build -t valexam:latest ."
}
  
stage('Push the image to dockerhub'){
sh "docker login -u 'vkageha' -p 'Imara@0001'"
sh "docker tag valexam:latest vkageha/valexam:version1"
sh "docker push vkageha/valexam:version1"
}

stage('Deploy (Docker run the image)')
{
sh "docker run -d -p 6612:80/tcp valexam:latest"
}
  
stage('Apply changes to the environment')
{
sh "ls -l"
}


}

