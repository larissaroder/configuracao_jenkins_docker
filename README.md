# Rodar o arquivo Docker Compose para fazer o pull da imagem do Jenkins

# Configurando o ambiente do Jenkins no Docker

Acessar o Container do Jenkins: 
$docker exec -it --user root jenkins /bin/bash

Efetuar o download do Maven:
$wget http://ftp.unicamp.br/pub/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz

Descompactar o arquivo do Maven:
tar -xvzf apache-maven-3.3.9-bin.tar.gz

Acessar o local descompactado no nosso exemplo será o local:
/opt/apache-maven-3.3.9

Configurar o Maven na variável de ambiente:
export M2_HOME=/opt/apache-maven-3.3.9 
export M2=$M2_HOME/bin
export PATH=$M2:$PATH

Verificar a instalação do Java, geralmente o caminho é /usr/lib/jvm/java-8-openjdk-amd64

Caso necessário configurar a variável de ambiente para o Java:
export JAVA_HOME=/opt/apache-maven-3.3.9 
export JAVA=$JAVA_HOME/bin
export PATH=$JAVA:$PATH

Após as Configurações acessar o endereço da URL do Jenkins

Acessar o log do Docker para pegar a chave inicial de instalação:
$docker logs -f <id_container>

# Gerenciar o Docker

1 - Clicar em Criar um Job, escolher a opção Construir um projeto de Software free style

2- Clicar em Global Tools Configuration
2.1 - Colocar o caminho do java Home na instalação do JDK
		/usr/lib/jvm/java-8-openjdk-amd64
	2.2 - Configurar a Opção Maven
		/opt/apache-maven-3.3.9
