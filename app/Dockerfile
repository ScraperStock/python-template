FROM python:3.8.10

# Setup env
ENV USER="ubuntu"
ENV GROUP="ubuntu"
ENV ROOT_DIR="/src"
ENV LANG C.UTF-8
ENV LC_ALL C.UTF-8
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONFAULTHANDLER 1
ENV PATH=/home/${USER}/.local/bin:$PATH
ENV FT_APP_ENV="docker"

RUN mkdir ${ROOT_DIR}/app -p

# RUN apt-get update \
#   && apt-get install -y curl  \
#   && apt-get clean

RUN useradd -u 1000 -G sudo -U -m -s /bin/bash ${USER}

RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

RUN chown ${USER}:${GROUP} ${ROOT_DIR} 

COPY --chown=${USER}:${GROUP} . ${ROOT_DIR}/app

WORKDIR ${ROOT_DIR}/app

USER ${USER}
RUN echo 'alias ll="ls -la"' >> ~/.bashrc

RUN pip install -r requirements.txt

# ENTRYPOINT ["tail", "-f", "/dev/null"]
#CMD ["main.py"]
#ENTRYPOINT ["python3"]