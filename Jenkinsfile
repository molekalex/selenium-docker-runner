pipeline{


agent any

parameters {
  choice choices: ['firefox', 'edge', 'chrome'], description: 'select the browser to test', name: 'BROWSER'
}


stages{
stage('stage1 - grid up'){
steps{
bat "docker-compose -f grid.yaml up --scale ${params.BROWSER}=1 -d"
echo "starting the grid..."
}
}

stage('stage2 - tests up'){
steps{
bat "docker-compose -f test-suites.yaml up --pull=always"
echo "starting the tests..."
}


}

post{
always{
bat "docker-compose -f grid.yaml down"
bat "docker-compose -f test-suites.yaml down"
archiveArtifacts artifacts: 'output/flight-portal/emailable-report.html', followSymlinks: false
archiveArtifacts artifacts: 'output/vendor-portal/emailable-report.html', followSymlinks: false
}
}

}

}