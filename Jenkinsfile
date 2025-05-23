pipeline{


agent any

stages{
stage('stage1 - containers UP, Run test '){
steps{
bat "docker-compose up"
echo "creating the grid, browsers, test containers..."
}
}
stage('stage2 - containers deleting'){
steps{
bat "docker-compose down"
echo "stopping and deleting created containers..."

}
}
}


}