FROM python:3.11.4-bookworm

# Set default values for build arguments
ARG MLFLOW_USERNAME=mlflow
ARG UID=1000
ARG GID=1000

RUN groupadd -g ${GID} mlflowuser
RUN useradd -g ${GID} -u ${UID} ${MLFLOW_USERNAME}

# Keeps Python from generating .pyc files in the container
ENV PYTHONDONTWRITEBYTECODE=1
# Turns off buffering for easier container logging
ENV PYTHONUNBUFFERED=1

# Install pip requirements
COPY requirements.txt .
RUN python -m pip install -r requirements.txt

WORKDIR /home/${MLFLOW_USERNAME}
RUN chown -R ${MLFLOW_USERNAME} /home/${MLFLOW_USERNAME}
USER ${MLFLOW_USERNAME}
