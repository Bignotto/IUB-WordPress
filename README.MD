IUB Wordpress
=============

Script para montar um servidor WordPress com Docker e Docker Compose.

## Configurações do servidor virtual

- Configure o hostname:

    `sudo nano /etc/hostname`

    `sudo nano /etc/hosts`

    Coloque o hostname em cada vez que o hostname default aparecer.


- Configure o IP:

    `sudo nano /etc/network/interfaces`

---

A partir de uma VM Linux executar as instruções abaixo.

Links:
- https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-18-04
- https://www.digitalocean.com/community/tutorials/como-instalar-e-usar-o-docker-no-ubuntu-18-04-pt
- https://www.digitalocean.com/community/tutorials/how-to-install-docker-compose-on-ubuntu-18-04-pt

 ## Configurações do Usuário

 Se você quiser evitar digitar sudo sempre que você executar o comando docker, adicione seu nome de usuário ao grupo docker:

`sudo usermod -aG docker ${USER}`

Para aplicar a nova associação ao grupo, efetue logout do servidor e faça logon novamente ou digite o seguinte:

`su - ${USER}`

Você será solicitado a entrar com seu usuário e senha para continuar.

Confirme que seu usuário está agora adicionado ao grupo docker digitando:

`id -nG`

O output deve ser:

`${USER} sudo docker`

## Update

`sudo apt update`

Algumas dependências:

`sudo apt install apt-transport-https ca-certificates curl software-properties-common`

---

## Instalar o Docker

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

`sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"`

`sudo apt update`

Certifique-se de que você irá instalar a partir do repositório do Docker em vez do repositório padrão do Ubuntu:

`apt-cache policy docker-ce`

Você verá uma saída como esta, embora o número da versão do Docker possa estar diferente:

`
docker-ce:
  Installed: (none)
  Candidate: 18.03.1~ce~3-0~ubuntu
  Version table:
     18.03.1~ce~3-0~ubuntu 500
        500 https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
`

Finalmente instalando o Docker:

 `sudo apt install docker-ce`

 Check:

 `sudo apt install docker-ce`

 ---

## Instalando Docker Compose

`sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-'uname -s'-'uname -m' -o /usr/local/bin/docker-compose`

Em seguida, vamos definir as permissões:

`sudo chmod +x /usr/local/bin/docker-compose`

Então, vamos verificar se a instalação foi bem sucedida verificando a versão:

`docker-compose --version`

Isso aparecerá na tela a versão que instalamos:

Output:
`docker-compose version 1.21.2, build a133471`
