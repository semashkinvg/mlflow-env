FROM continuumio/anaconda3
EXPOSE 5000

RUN apt-get -y install curl \
    && apt-get -y install telnet

RUN pip install --upgrade pip \
    && pip install mlflow \
    && pip install azure-storage \
    && pip install numpy \
    && pip install scipy \
    && pip install pandas \
    && pip install scikit-learn \
    && pip install cloudpickle

ENTRYPOINT ["mlflow","server","--expose-prometheus=./metrics","--host=0.0.0.0"]

