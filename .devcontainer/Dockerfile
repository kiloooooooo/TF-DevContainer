FROM tensorflow/tensorflow:2.15.0-gpu

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get install -y apt-utils

RUN apt-get install -y libgl1-mesa-dev graphviz && \
    pip install opencv-python tqdm einops pydot matplotlib pandas

# VSCode Pylance用の設定
WORKDIR /tf-pylance-patch
COPY ../tensorflow-pylance.patch .
RUN cat tensorflow-pylance.patch >> /usr/local/lib/python3.11/dist-packages/tensorflow/__init__.py

WORKDIR /
