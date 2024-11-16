# ECM401 - Projeto de Business Intelligence - DataMart

Projeto de Business Intelligence - DataMart para a disciplina **ECM401 - Banco de Dados**, ministrada pelo professor [Antônio Guardado](https://www.linkedin.com/in/antonio-fernando-nunes-guardado-7bb40b135/).

# Sumário
  - [Dataset](#dataset)
  - [Como rodar](#como-rodar)
    - [Vídeo passo a passo](#vídeo-passo-a-passo)
    - [Instruções - VS Code](#instruções---vs-code)
  - [Como criar um ambiente virtual](#como-criar-um-ambiente-virtual)
    - [Unix](#unix)
    - [Windows](#windows)
- [Autores](#autores)

# Dataset

O dataset utilizado foi a base de microdados do ENEM 2023, disponível nesse link: [Microdados do ENEM 2023](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem)

## Como rodar

### Vídeo passo a passo


### Instruções - VS Code

1. Coloque o arquivo baixado `MICRODADOS_ENEM_2023.csv` na pasta `datasets/` na raiz do projeto.
2. Rode o servidor MySQL localmente. Duas opções fáceis são:
   1. Usando o MySQL Server
   2. Usando imagem Docker do MySQL
      1. Baixe a imagem do MySQL:
         ```bash
         docker pull mysql
         docker run --name mysql -e MYSQL_ROOT_PASSWORD=root -dp 3306:3306 mysql
         ```
> A URL será `localhost` com usuário `root` e senha `root` e a porta `3306`.
> 
3. Crie os schemas no MySQL.

```sql
CREATE SCHEMA `ENEM_OLTP`;
CREATE SCHEMA `ENEM_DM`;
```

4. Crie um ambiente virtual e instale as dependências. Veja como criar um ambiente virtual [aqui](#como-criar-um-ambiente-virtual).
5. Instale as extensões do `Jupyter Notebooks` disponíveis nesse [link](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) .
6. Rode o script dentro dos notebooks numerados de 1 a 6.

## Como criar um ambiente virtual

### Unix

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```
# Autores

- [Enzo Sakamoto](https://linkedin.com/in/enzosakamoto)
- [Flavio Murata](https://linkedin.com/in/02mrt/)
- [Vinicius Berti](https://linkedin.com/in/vinicius-berti-a80354209/)