pipeline{


agent any

stages{
stage('containers UP, Run test '){
steps{
bat "docker-compose up"
echo "creating the grid, browsers, test containers"
}
}
stage('stage-2'){
steps{
bat "docker-compose down"
echo "pushing docker image"

}
}
}


post{
always {
echo "post actions"
}
}

}