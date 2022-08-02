pipeline{
    agent any
    stages{
        stage('one'){
            steps{
                echo "Hi, This is stage one"
            }
        }
        stage('Two'){
            steps{
                echo "Hi, This is stage Two"
            }
        }
        stage('Three'){
            steps{
                echo "Hi, This is stage Three"
            }

        }
        stage('four'){
            parallel{
                stage('unit test'){
                    steps{
                        echo "Runing test"
                    }
                }
                stage('Integration test'){
                    agent{
                        docker{
                            reuseNode false
                            image 'ubuntu'
                        }
                    }
                    steps{
                        echo "Runing Integration testing."
                    }
                }
            }
        }
    }
}