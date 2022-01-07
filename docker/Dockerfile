FROM dockerhub.ir/python:3.9.9-slim-buster

WORKDIR /var/www/
RUN chown -R www-data: /var/www
USER www-data
ENV PATH="/var/www/.local/bin:${PATH}"

COPY ["requirements.txt", "/var/www/"]
RUN pip install -r requirements.txt

COPY [".", "/var/www"]
ENV FLASK_APP=main
CMD flask run --host 0.0.0.0
