FROM python:3.7.6-alpine3.11

WORKDIR /opt/
COPY requirements.txt /opt/
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories
RUN apk add build-base
RUN pip install --no-cache-dir -r /opt/requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
EXPOSE 80
CMD ["gunicorn", "api:app", "-c", "./gunicorn.conf.py"]