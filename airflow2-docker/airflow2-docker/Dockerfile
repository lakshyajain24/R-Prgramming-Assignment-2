FROM apache/airflow
USER root

ARG AIRFLOW_HOME=/opt/airflow
ADD dags /opt/airflow/dags

RUN pip install --upgrade pip

USER airflow
RUN pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org boto3
RUN pip install --upgrade pip
COPY requirements.txt /opt/airflow
WORKDIR /opt/airflow
RUN pip install -r requirements.txt


USER ${AIRFLOW_UID}