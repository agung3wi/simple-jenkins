node {
    checkout scm
    docker.image('agung3wi/alpine-rsync:1.1').inside('-u root') {
        sshagent (credentials: ['ssh-pttas-server-lokal']) {
            sh 'mkdir -p ~/.ssh'
            sh 'ssh-keyscan -H "pttas.xyz" > ~/.ssh/known_hosts'
            sh "rsync -rav --delete . pttas@pttas.xyz:/home/admin/web/simple-jenkins.appdemo.online/public_html --exclude=.git"
        }
    }
}
