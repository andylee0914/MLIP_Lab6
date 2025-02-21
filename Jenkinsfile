pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo "Test Step: Running pytest via conda"

                # Initialize conda for bash (if required)
                sudo /Users/andylee/miniconda3/condabin/conda init

                # Run pytest using the specified conda environment.
                # Replace "myenv" with the actual name of your conda environment.
                sudo /Users/andylee/miniconda3/condabin/conda run -n mlip pytest
                '''

            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our porject'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
