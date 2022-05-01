node {
    stage('Git checkout') {
        git branch: "${params.BRANCH}", url: 'https://github.com/Projet-Automation-Infra-SI-Ynov/Deploy_k3s'
    }
    stage('Add k3s-master IP address to the token to join worker with his')
        sh "sed -i 's/###IP_MASTER###/${params.MASTER_IP}/g' ./k3s-worker/tasks/main.yml "
    stage('Execute playbook') {
        sh "ansible-playbook -i ./inventory.ini ./playbook.yml"
    }
}