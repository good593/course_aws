FROM python:3.12-slim

RUN apt update && apt install nginx -y

# 파이썬 모듈 설치 
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

# Nginx
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

# Django server
COPY ./django-server /app
WORKDIR /app

# 환경변수 적용 
ENV SECRET_KEY 'django-insecure-yq9quc!!j!@^p-(ez^o%sb&-jxnq@z@)@di-unm14wp8smed9h'

COPY run.sh .
RUN chmod +x run.sh
CMD ["./run.sh"]

