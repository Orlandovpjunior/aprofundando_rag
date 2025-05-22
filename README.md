
````md
# 📚 aprofundando_rag

## 🚀 Para rodar o projeto:

### 1. Suba o container do Elasticsearch

```bash
docker run -p 127.0.0.1:9200:9200 -d --name elasticsearch \
  -e "discovery.type=single-node" \
  -e "xpack.security.enabled=false" \
  -e "xpack.license.self_generated.type=trial" \
  -v "elasticsearch-data:/usr/share/elasticsearch/data" \
  docker.elastic.co/elasticsearch/elasticsearch:8.15.0
````

> 🔗 [Imagem no DockerHub](http://docker.elastic.co/elasticsearch/elasticsearch:8.15.0)

### 2. Instale as dependências do projeto

```bash
pip install -r requirements.txt
```

### 3. Inicie o Elasticsearch (caso o container esteja parado)

```bash
docker start elasticsearch
```

### 4. Conecte o backend ao Elasticsearch

Dentro da pasta `backend`, execute:

```bash
python index_data_raw.py
```

### 5. Rode a API FastAPI

Ainda na pasta `backend`, execute:

```bash
fastapi dev main.py
```

### 6. Suba o frontend

Dentro da pasta `frontend`, execute:

```bash
npm install
npm run serve
```
