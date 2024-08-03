## Configurer Minikube et Kubectl pour Jenkins :

`sudo mkdir -p /var/lib/jenkins/.kube`
Explication de la commande ci-dessus : -

### 1) sudo mkdir -p /var/lib/jenkins/.kube : 
- Cette commande crée un répertoire nommé .kube dans le `/var/lib/jenkins/répertoire`. 
Ce répertoire est généralement utilisé pour stocker les fichiers de configuration de Kubernetes.

`sudo cp /home/moussa/.kube/config /var/lib/jenkins/.kube/config`

### 2) sudo cp /home/moussa/.kube/config /var/lib/jenkins/.kube/config:-
Cette commande copie un fichier de configuration Kubernetes (kubeconfig) du /path/to/your/kubeconfigrépertoire spécifié .kube dans le répertoire personnel de l'utilisateur Jenkins ( /var/lib/jenkins/). Ce fichier kubeconfig contient des informations sur la façon de se connecter à un cluster Kubernetes.

`sudo chown jenkins:jenkins /var/lib/jenkins/.kube/config`

### 3) sudo chown jenkins:jenkins /var/lib/jenkins/.kube/config:-
Cette commande modifie la propriété du fichier kubeconfig copié à l'utilisateur jenkinset au groupe jenkins. 
Elle garantit que le processus Jenkins dispose des autorisations nécessaires pour lire et utiliser le fichier kubeconfig.

`sudo chmod -R +r /home/moussa/.minikube/`

### 4) sudo chmod -R +r /home/moussa/.minikube/ :-
Cette commande accorde +rdes autorisations de lecture ( ) de manière récursive ( -R) à tous les fichiers et répertoires sous 
/home/moussa/.minikube/. Il est utilisé pour garantir que Jenkins dispose d'un accès en lecture au répertoire Minikube et à son contenu, qui peut inclure des fichiers tels que la clé client nécessaire à la configuration Kubernetes de Minikube.

