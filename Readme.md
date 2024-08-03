## ARCHITECTURE DU PROJET

![image](https://github.com/user-attachments/assets/377329f4-3d43-40a2-a896-2a8dd7f56c9d)

Étape 1 – Enregistrez/transférez votre code sur GitHub

Étape 2 – Extrayez votre code de GitHub vers votre serveur Jenkins

Étape 3 – Utilisez l’outil de création Gradle/Maven pour créer les artefacts

Étape 4 – Créer une image Docker

Étape 5 – Envoyez votre dernière image Docker vers DockerHub

Étape 6 – Extrayez la dernière image de DockerHub dans Jenkins.

Étape 7 – Utilisez ensuite k8s-spring-boot-deployment.yml pour déployer votre application dans votre cluster Kubernetes.

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

