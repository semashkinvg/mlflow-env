FROM continuumio/anaconda3

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update --fix-missing && \
    apt-get upgrade -y && \
    apt-get -y install curl && \
    apt-get -y install telnet && \
    apt-get -y install vim

RUN conda update conda -y && \
    conda install -c conda-forge jupyterlab

ADD requirements.txt .
RUN pip install -r requirements.txt
RUN git clone https://github.com/mlflow/mlflow-example.git

EXPOSE 8888
CMD ["/bin/bash","-c","/opt/conda/bin/jupyter notebook --notebook-dir=/opt/notebooks --ip='*' --port=8888 --no-browser --allow-root"]