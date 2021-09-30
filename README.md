# Ansible_Docker
Script de automação no Ansible

Objetivo: 

Instalação do software ElasticSearch

![monitoring-cluster-alerts](https://user-images.githubusercontent.com/90550531/135507243-84cbd343-8e05-4134-85b2-522d1cf3ab96.gif)

** Recomendado clonar o repositório Ansible_Docker para realizar a instalação completa **

# Código 
---
- hosts: 
     {Altere e coloque o nome do grupo de hosts}
		 
  remote_user: 
  
 	{Usuário para efetuar a comunicação e executar os scripts}
		
  roles:
    - Docker
    - Portainer
    - Elastic

---
Explicação sobre cada item:

- Hosts: 
	
  Neste campo coloque o nome do grupo que você definiu no arquivo de configuração host.yml
	
- remote_user: 

  Usuário cadastrado na máquina destino para efetuar a comunicação e execução dos scripts
	
- roles: 

  Logo abaixo desse campo seguido - informe o nome das regras que será acionada. 
  
# Etapa de instalação  
---  

1º Passo

- Copie o link do repositório no seu Git Hub

![Git](https://user-images.githubusercontent.com/90550531/135503920-dbb3868f-411c-41de-8a07-6ea7d65d43f4.png)

2º Passo

- Dentro do servidor onde está instalado o Ansible, rode o comando: git clone {LINK DO REPOSITÓRIO COPIADO}

![clone](https://user-images.githubusercontent.com/90550531/135504035-82c0afb7-85b5-4193-b46f-5a018becac57.png)

3º Passo

- Rode um comando editor de texto de sua preferência (vim,nano ou vi) e o nome do arquivo docker.yml

4º Passo

- Conforme definido no arquivo hosts.yml, copie o nome do grupo onde você colocou o IP da máquina que deseja realizar essas instalações.
- Coloque o nome do usuário com permissões no visudo para realizar a comunicação entre os servidores via ssh.

######  Preferência não utilize usuário root nesse campo ######

5º Passo

- Depois dessas alterações rode comando para executar a sua playbook

	 Command: ansible-playbook elastic.yml 

######  Caso queira debugar o arquivo pode rodar conforme abaixo ######	

	Command: ansible-playbook elastic.yml -vvv

