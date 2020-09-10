FROM ubuntu

LABEL version=1.0
LABEL description="Esta es una imagen de apache con una web adjunta"
LABEL vendor=JMATOSP

ENV TZ=America/Lima

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update
RUN apt-get install apache2 -y

WORKDIR /var/www/html

COPY webapp .

ENV contenido JESUS_MATOS

RUN echo "$contenido" > prueba.html

RUN echo "$(whoami)" > user1.html

RUN useradd jesus

USER jesus

RUN echo "$(whoami)" > /tmp/user2.html

USER root

RUN cp /tmp/user2.html /var/www/html/user2.html

COPY run.sh /run.sh

CMD sh /run.sh