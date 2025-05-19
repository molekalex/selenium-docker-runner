pipeline{


agent any

stages{
stage('stage 1 - start grid'){
steps{
bat "docker-compose -f grid.yaml -d"
echo "starting the grid"
}
}
stage('stage 2 - start the test'){
steps{
bat "docker-compose -f test-suites.yaml"
echo "running the tests"

}
}


}


post{
always {
bat "docker-compose -f test-suites.yaml down"
bat "docker-compose -f grid.yaml down"
echo "deleting the containers..."
}
}

}