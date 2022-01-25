#apos criar o dockerfile, executar o docker build
#docker build -t murillomamud/rotten-potatoes:v1 .
#para upar no docker hub:
#docker push <nome da imagem>:versao
# para criar versao latest:
#docker tag <imagem>:versao <image>:latest
#docker push <imagem>:latest
#para subir kubernets:
# k3d cluster create meucluster --agents 3 --servers 3 -p "8080:30000@loadbalancer"
FROM python:3.8-slim-buster
WORKDIR /app
COPY requirements.txt .
RUN python -m pip install -r requirements.txt
COPY . /app
EXPOSE 5000
CMD ["gunicorn", "--workers=3", "--bind", "0.0.0.0:5000", "-c", "config.py", "app:app"]
