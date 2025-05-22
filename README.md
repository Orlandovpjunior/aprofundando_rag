# aprofundando_rag

# Para rodar o projeto:
Rode o container:

`docker run -p 127.0.0.1:9200:9200 -d --name elasticsearch \
-e "discovery.type=single-node" \
-e "xpack.security.enabled=false" \
-e "xpack.license.self_generated.type=trial" \
-v "elasticsearch-data:/usr/share/elasticsearch/data" \
[docker.elastic.co/elasticsearch/elasticsearch:8.15.0](http://docker.elastic.co/elasticsearch/elasticsearch:8.15.0)`

Depois:

docker start elasticsearch

Dentro da pasta backend faça a conexão:

python index_data_raw.py

Rode a api:

fastapi dev main.py

Dentro da pasta frontend:

npm i

npm run serve
