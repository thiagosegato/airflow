# Apache Airflow
Inicie o Apache Airflow em sua máquina. Este projeto roda somente em Linux!


## Configurando o projeto
1. Clone o projeto:
    ```bash
    git clone https://github.com/thiagosegato/airflow.git
    ```
2. Acesse a pasta:
    ```bash
    cd airflow-windows
    ```
    2.1. <i>Passo Opcional</i>: A partir daqui você poderá optar a utilizar o Vscode. Caso prefira, digite o comando abaixo:
      ```bash
      code .
      ```
      * Dica: Você pode iniciar um terminal dentro do próprio Vscode para continuar a configurar o projeto!
3. Crie um ambiente virtual python:
    ```
    python3 -m venv .venv
    source .venv/bin/activate
    ```
4. Instale o Airflow e as bibliotecas necessárias:
    ```
    AIRFLOW_VERSION=2.6.3
    PYTHON_VERSION="$(python3 --version | cut -d " " -f 2 | cut -d "." -f 1-2)"
    CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"
    pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}" beautifulsoup4 lxml pandas
    ```

## Rodando o projeto
1. <i>Passo Opcional</i>: Ative o ambiente virtual python caso não esteja:
    ```
    source .venv/bin/activate
    ```
2. Inicie o Airflow com 2 variáveis de ambiente:
    ```
    export AIRFLOW_HOME=$(pwd)
    export AIRFLOW__CORE__LOAD_EXAMPLES=False
    airflow standalone
    ```

## Acessando a ferramenta
Acesse [http://localhost:8080/](http://localhost:8080/)<br>
Usuário: admin<br>
Senha: Copie a senha no arquivo `standalone_admin_password.txt`

## Links úteis
- [Apache Airflow](https://airflow.apache.org/)
- [NBA Data Crawler](https://github.com/caiocolares/nba-crawler-airflow)
- [Agendamentos e rodagens das DAGs](https://airflow.apache.org/docs/apache-airflow/stable/core-concepts/dag-run.html)
- [Crontab Guru](https://crontab.guru/)

## Bibliotecas utilizadas além do Apache Airflow
- [Airflow](https://airflow.apache.org/)
- [Pandas](https://pandas.pydata.org/)
- [BeautifulSoup4](https://pypi.org/project/beautifulsoup4/)
