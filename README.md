# ECM401 - Projeto de Business Intelligence - DataMart

Projeto de Business Intelligence - DataMart para a disciplina **ECM401 - Banco de Dados**, ministrada pelo professor [Antônio Guardado](https://www.linkedin.com/in/antonio-fernando-nunes-guardado-7bb40b135/).

# Sumário
- [Dataset](#dataset)
- [Modelo da base operacional (OLTP)](#modelo-da-base-operacional-oltp)
- [Modelo Dimensional - DataMart](#modelo-dimensional---datamart)
- [Construções Analíticas](#construções-analíticas)
- [Visualização dos Dados](#visualização-dos-dados)
- [Como rodar o projeto](#como-rodar-o-projeto)
    - [Vídeo com passo a passo](#vídeo-com-passo-a-passo)
    - [Instruções - VS Code](#instruções---vs-code)
  - [Como criar um ambiente virtual](#como-criar-um-ambiente-virtual)
    - [Unix](#unix)
    - [Windows](#windows)
- [Autores](#autores)

# Dataset

O dataset utilizado foi a base de microdados do ENEM 2023, disponível nesse link: [Microdados do ENEM 2023](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem)

# Modelo da base operacional (OLTP)

O modelo OLTP foi criado com base no dataset do ENEM 2023, com a finalidade de armazenar os dados de forma normalizada. Arquivo `.mwb` disponível [aqui](./modelos/Modelo-OLTP.mwb).

![Modelo OLTP](./modelos/OLTP.png)

# Modelo Dimensional - DataMart

O modelo dimensional foi criado com base no modelo OLTP, com a finalidade de otimizar as consultas e análises de dados. Arquivo `.mwb` disponível [aqui](./modelos/Modelo-DM.mwb).

![Modelo Dimensional](./modelos/DM.png)

# Construções Analíticas

Foram criadas cinco consultas com funções analíticas, contendo dois ou três agrupamentos, disponíveis no seguinte notebook: [aqui](./src/5%20-%20Selects%20analíticos.ipynb)

# Visualização dos Dados

Com o uso das bibliotecas pandas, numpy e matplotlib do Python, criamos seis gráficos com as informações extraídas da base. As visualizações podem ser executadas no seguinte notebook: [aqui](./src/6%20-%20Visualização%20dos%20dados.ipynb)

# Como rodar o projeto

### Vídeo com passo a passo

[![Vídeo com passo a passo](https://img.youtube.com/vi/NzI7v51CfVo/sddefault.jpg)](https://youtu.be/NzI7v51CfVo)

***Obs:** no vídeo não foi mencionado como criar um ambiente virtual para instalar as dependências, mas as instruções podem ser encontradas [aqui](#como-criar-um-ambiente-virtual).*

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
3. Crie os schemas no MySQL. Duas opções fáceis são:
   1. Usando o MySQL Workbench
   2. Rodando via CLI os scripts SQL abaixo:

```sql
CREATE SCHEMA `ENEM_OLTP`;
CREATE SCHEMA `ENEM_DM`;
```

4. Crie um ambiente virtual e instale as dependências. Veja como criar um ambiente virtual [aqui](#como-criar-um-ambiente-virtual).
5. Instale as extensões do `Jupyter Notebooks` disponíveis nesse [link](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) .
6. Rode o script dentro dos notebooks numerados de 1 a 6.

## Como criar um ambiente virtual

Crie um ambiente virtual para instalar as dependências do projeto.

### Unix

```bash
python3 -m venv .venv
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