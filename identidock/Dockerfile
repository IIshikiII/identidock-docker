FROM python:3.9

RUN groupadd -r uwsgi && useradd -r -g uwsgi uwsgi
# RUN apt-get update && apt-get install -y \
#     gcc \
#     build-essential \
#     && rm -rf /var/lib/apt/lists/*
    
RUN pip install Flask==2.3.2 uWSGI==2.0.20 requests redis
WORKDIR /app
COPY app /app/
COPY cmd.sh /

EXPOSE 9090 9191

USER uwsgi

CMD ["/cmd.sh"]