# Apache Airflow instalação
Vamos então começar criando um ambiente virtual em Python, na versão 3.7.
```
mkdir datapipeline
cd datapipeline
python3 -m venv .env
source .env/bin/activate
```
Criaremos uma variável de ambiente que aponta para a pasta onde o Airflow será instalado:
```
export AIRFLOW_HOME=$(pwd)/airflow
```
Lembre sempre de manter esta variável ativa, caso contrário o Airflow será criado na pasta raiz do usuário. Feito isso, instalaremos o Airflow em nosso ambiente, aqui estamos usando a versão 1.10.14:
```
pip install apache-airflow==1.10.14 --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-1.10.14/constraints-3.7.txt"
```
Após instalar Airflow, iniciaremos o banco de dados da ferramenta:
```
airflow initdb
```
E para iniciar o serviço Webserver, responsável pela interface da ferramenta, digitaremos:
```
airflow webserver
```
Acessaremos a interface do Airflow no navegador usando o link: http://localhost:8080.

E para iniciarmos o serviço Scheduler, responsável pelo agendamento de tarefas para execução, digitaremos:
```
airflow scheduler
```
