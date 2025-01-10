FROM mcr.microsoft.com/dotnet/sdk:8.0
# RUN cp /bin/bash /bin/sh
RUN apt-get update -y && apt-get install python3 python3-venv python3-pip git -y
RUN apt-get install unixodbc-dev -y
COPY requirements.txt /tmp/deps/

WORKDIR /home
RUN python3 -m venv .venv \
    && . .venv/bin/activate \
    && pip install --no-cache-dir --disable-pip-version-check -r /tmp/deps/requirements.txt \
    && rm -rf /tmp/deps
