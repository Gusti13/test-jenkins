def remote = [:]
remote.name = "node-1"
remote.host = "jktols04.radmond.com"
remote.allowAnyHosts = true
remote.port = 22022

// folder project
def root_folder = "/home/rhema"
def main_folder = "deboos"
def sub_folder = "frontend"

// githab repo
def repo = "git@github.com:Gusti13/reactjs-counting.git"
def branch = "main"

// aplikasi
def port = 8282
def pm2 = "run"

def folder = "${root_folder}/${main_folder}/${sub_folder}";

node {
    withCredentials([sshUserPrivateKey(credentialsId: 'rhema-ssh', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'rhema')]) {
        remote.user = rhema
        remote.identityFile = identity
        remote.connection = "ssh -i '${identity}' -p ${remote.port} ${rhema}@${remote.host}"
        stage("SSH GIT PULL") {
          sh "${remote.connection} 'node -v'"
        }
    }
}
