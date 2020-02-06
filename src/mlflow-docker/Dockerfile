FROM continuumio/anaconda3
EXPOSE 5000

RUN apt-get -y install curl \
    && apt-get -y install telnet \
    && apt-get -y install vim

RUN pip install --upgrade pip \
    && pip install mlflow \
    && pip install azure-storage \
    && pip install numpy \
    && pip install scipy \
    && pip install pandas \
    && pip install scikit-learn \
    && pip install cloudpickle
RUN mkdir /artifacts
ENTRYPOINT ["mlflow","server","--expose-prometheus=./metrics","--default-artifact-root=s3://mlflow/artifacts","--backend-store-uri=/mlflow","--host=0.0.0.0"]

