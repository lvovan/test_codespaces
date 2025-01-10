FROM mcr.microsoft.com/dotnet/sdk:8.0
# RUN cp /bin/bash /bin/sh
RUN apt-get update -y && apt-get install python3 python3-venv python3-pip git -y
RUN apt-get install unixodbc-dev -y

WORKDIR /work

RUN python3 -m venv .venv
COPY . .
RUN . .venv/bin/activate && pip install -r requirements.txt
