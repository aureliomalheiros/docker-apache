FROM debian

RUN apt-get update && apt-get install -y apache2
RUN chown www-data:www-data /var/lock & chown www-data:www-data /var/run && chown www-data:www-data /var/log
ENV APACHE_LOCK_DIR="/var/lock"
ENV APACHE_PID_FILE="/var/run/apache2.pid"
ENV APACHE_RUN_USER="www-data"
ENV APACHE_RUN_GROUP="www-data"
ENV APACHE_LOG_DIR="/var/log/apache2"

#COPY copia o arquivo de diretórios para o container
#COPY index.html /var/www/html/

#ADD copia um arquivo de diretório para o container, porém ele consegue copiar um arquivo tar extraido
#Consegue fazer um Download de um arquivo remoto e enviar para o container
ADD index.html /var/www/html

LABEL description="Meu-Web-Service"


#Usuário padrão é o www-data ao invés do root
#Vou usar root por conta das permissões nas portas
USER root

#Defini o diretório default do container
WORKDIR /var/www/html

VOLUME /var/www/html
EXPOSE 80

ENTRYPOINT ["/usr/sbin/apachectl"]
CMD ["-D", "FOREGROUND"]
