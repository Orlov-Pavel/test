node("linux"){
    stage("Git checkout"){
        git credentialsId: '5ac0095d-0185-431b-94da-09a0ad9b0e2c', url: 'https://github.com/aragastmatb/example-playbook.git'
    }
    stage("define prod_run"){
        prod_run=false
    }
    stage("Run playbook"){
        if (prod_run){
            sh 'ansible-playbook site.yml -i inventory/prod.yml --check --diff'
        }
        else{
            sh 'ansible-playbook site.yml -i inventory/prod.yml'
        }
        
    }
}