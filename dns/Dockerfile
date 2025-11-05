# Base da imagem
FROM ubuntu:latest 

# O comando RUN serve para executar um comando na imagem
# Nesse caso abaixo, estamos atualizando repositórios de pacotes
RUN apt update -y && apt install bind9 dnsutils -y

RUN mkdir -p /etc/bind && chown -R bind:bind /etc/bind


# Copia arquivo para dentro da imagem
COPY named.conf.lab /etc/bind

COPY db.siteA.lab /etc/bind

COPY db.siteB.lab /etc/bind


# Todo container docker precisa de um ponto de entrada/execução para 
# manter o container em funcionamento
# ENTRYPOINT [ "executable" ]
# No caso abaixo, o serviço chamado named (bind) é executado em primeiro plano
EXPOSE 53/tcp
EXPOSE 53/udp

CMD ["/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]