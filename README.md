# Senac Banco de Dados Big Data

Projeto desenvolvido nas aulas da Pos-graduação de Big Data. Está aplicação contém um código python que será utilizada para normalização dos dados e ingestão dos dados para o bancos de dados em batch.

### Pré-requisitos
1. Instalações:
    - [Python](https://www.python.org/downloads) >= 3.8.10
    - Instalação das libs no requirements
    - jupyter notebook
2. Crie um ambiente virtual python na raiz do projeto e ative:
```
python -m venv .venv
./.venv/Scripts/activate
```
3. instalando as libs do projeto:
```
pip3 instal -r requiments.txt
```

### Caso opte por installar os container docker com o banco de dados mysql conforme realizei no projeto
1. Instalações:
    - as instruções para download da imagem e acesso usuário root estão nesse link https://hub.docker.com/r/mysql/mysql-server
2. Após a criação criei um usuário root com todos privilegios elevados para acessar o banco de dados com ip externo do container docker:
```
CREATE USER 'root'@'%' IDENTIFIED BY 'Senac#2022';
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
```
3. Pegar o IP da máquina que está rodando o container:
```
sudo docker ps "para pegar o container_id"
sudo docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' "CONTAINER_ID"
```

### Database
- senac (schema/collection)
    - tb_docente
    - tb_disciplina

### Arquivo plano csv
- contempla dos registros não normalizados que deverão ser tratados pelo pandas
