# Base da imagem
FROM ubuntu:latest 

# O comando RUN serve para executar um comando na imagem
# Nesse caso abaixo, estamos atualizando repositórios de pacotes
RUN apt update -y && apt install postfix mailutils -y

EXPOSE 25

CMD ["/usr/sbin/postfix", "start-fg"]

