FROM ubuntu:20.04

# installer le paquet python-virtualenv, ce qui permettra de créer des environnements 
# de travail virtual : virtualenv
RUN apt -y update;
RUN apt install -y python-virtualenv sshpass;

# créer un simple utilisateur
RUN adduser ${USER} && \
    echo ${PASSWORD} | passwd ${USER} --stdin

# créer l'environnement de travail virtuel
RUN virtualenv ansible2.7.10

# activer l'environnement virtuel
RUN source ansible2.7.10/bin/activate

# installer Ansible dans l'environnement virtuel
RUN pip install ansible==2.7.10

# vérifier la version de Ansible 
RUN ansible --version

# vérifier l'installation
RUN ls ansible2.7.10/bin/ansible* -l

# garder le container démarrer
CMD tail -F anything