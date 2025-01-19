# Vagrant Proxmox Cluster

Ce projet permet de déployer et de gérer un cluster Proxmox en utilisant Vagrant. Il fournit une solution rapide pour configurer des environnements Proxmox à des fins de test ou d'apprentissage.

## Prérequis

- [Vagrant](https://www.vagrantup.com/)
- [KVM](https://linux-kvm.org/)
- [Ansible](https://www.ansible.com/)

## Installation

1. Clonez ce dépôt sur votre machine locale :

   ```bash
   git clone https://github.com/florianspk/vagrant-proxmox-cluster.git
   ```

2. Accédez au répertoire du projet :

   ```bash
   cd vagrant-proxmox-cluster
   ```

3. Modifiez le fichier `settings.yaml` pour adapter les configurations à votre environnement, notamment les adresses IP, les noms d'hôte, et autres paramètres.

## Utilisation

Pour déployer le cluster Proxmox, exécutez la commande suivante :

```bash
vagrant up
```

Cette commande :

- Créera les machines virtuelles définies dans le fichier `Vagrantfile`.
- Configurera chaque machine selon les paramètres prévus dans `settings.yaml`.

### Commandes utiles

- **Arrêter les machines** :

  ```bash
  vagrant halt
  ```

- **Redémarrer les machines** :

  ```bash
  vagrant reload
  ```

- **Détruire les machines** (attention, toutes les données seront perdues) :

  ```bash
  vagrant destroy
  ```

## Structure du projet

- **`Vagrantfile`** : Contient la définition des machines virtuelles, leurs ressources (RAM, CPU, etc.), et les scripts de provisionnement.
- **`settings.yaml`** : Fichier de configuration permettant de personnaliser les adresses IP, noms d’hôtes et autres paramètres.
- **Dossier `hack`** : Contient des scripts ou outils supplémentaires pour personnaliser le cluster.

## Personnalisation

- **Ajout de machines** : Modifiez le `Vagrantfile` pour inclure plus de nœuds dans le cluster.
- **Configuration avancée** : Utilisez Ansible ou d'autres outils pour automatiser la configuration interne des machines.

