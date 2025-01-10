FROM mcr.microsoft.com/vscode/devcontainers/dotnet:8.0
RUN apt-get update -y && apt-get install python3 python3-venv python3-pip git unixodbc-dev -y
COPY requirements.txt /tmp/deps/

ARG VENV_PATH="/home/vscode/venv"

RUN su vscode -c "python3 -m venv ${VENV_PATH}"  \
    && . ${VENV_PATH}/bin/activate \
    && pip install --no-cache-dir --disable-pip-version-check -r /tmp/deps/requirements.txt \
    && rm -rf /tmp/deps
