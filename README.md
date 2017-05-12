# Docker
Docker é uma plataforma Open Source escrito em Go, que é uma linguagem de programação de alto desempenho desenvolvida dentro do Google, que facilita a criação e administração de ambientes isolados.

Tutorial de instalação do Docker no ubuntu com apache

Instalação do Docker com Imagem

Entrar no link abaixo e baixar a última versão.
https://download.docker.com/linux/ubuntu/

Droplet do Ubuntu 16.04 64 bits Usuário não-root com privilégios sudo (Initial Setup Guide for Ubuntu 16.04 explica como configurar isto). Nota: O Docker requer uma versão de 64 bits do Ubuntu, bem como uma versão de kernel maior ou igual a 3.10. O Droplet padrão de 64 bits do Ubuntu 16.04 atende a esses requisitos.

Finalmente, instale o Docker:

sudo apt-get install -y docker-engine O Docker agora será instalado, o daemon iniciado, e o processo habilitado para iniciar no boot.

Verifique que ele está executando:

sudo service docker status A saída deve ser similar ao seguinte, mostrando que o serviço está ativo e em execução: [secondary_label Output] docker.service - Docker Application Container Engine Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled) Active: active (running) since Sun 2016-05-01 06:53:52 CDT; 1 weeks 3 days ago Docs: https://docs.docker.com Main PID: 749 (docker)

Próximo passo é subir a imagem Docker com Apache

Imagem docker criada para servir como base de estudos ao servidor web apache.

Utilize: A maquina chicocx é a do professor onde está a imagem. sudo docker run -dit --name apache-app --publish=9081:80 chicocx/docker-apache Para configurar externamente à imagem docker o local onde o apache salvará o site, utilize:

sudo docker run -dit --name apache-app --publish=9081:80 -v "$PWD":/usr/local/apache2/htdocs/ chicocx/docker-apache Entrar na máquina/imagem

docker exec -it [aqui é o nome do root da maquina imagem] bash sair sem encerrar a máquina:

ctrl p q Lista o status dos containers

docker ps -a Exclui os containers que estão parados

docker rm $(docker ps -q -f status=exited) Lista as imagens baixadas

docker images Exclui alguma imagem

docker rmi f72216345d97


