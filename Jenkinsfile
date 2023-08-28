pipeline{
    agent any
    parameters {
        string(name:"Person",defaultValue:"Shubham",description:"string param test description")
        boolParam(name:"Deploye",defaultValue:true,description:"boolean param test description")
        password(name:"Pass",description:"passsword param test description")
        choice(name:"Locations",choices:["US","UK","IND"],description:"choices param test description")
    }
    environment{
        name = "shubham"
        age = 16
    }
    stages{
        stage("get code"){
            steps{
                echo "getting code from git hub"
                sh '''
                echo "printing enc name : ${name}"
                sleep 3
                '''
            }
        }
        stage("build code"){
            steps{
                echo "building code"
                sh '''
                sleep 3
                ls
                pwd
                date
                cal
                echo "printing env age: ${age}"
                '''
            }
        }
        stage("deploy dev"){
            steps{
                echo "deploying code to dev"
                sh '''
                ls
                pwd
                cal
                sleep 4
                '''
            }
        }
        stage("deploy prod"){
            input {
                message "do you want to deploy to prod"
                ok "yes, proceed pls"
            }
            steps{
                echo "deplpoying to prod"
                sh '''
                sleep 5
                '''
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
