# Deploying Datu AI Analyst as container service

Use below recommended method to run Datu application as container service.

## Containerization

To deploy your Datu, you need to containerize it using Podman or Docker. The Dockerfile defines how your application is packaged and run. Below is an example Docker file that installs all needed dependencies, the application, and configures the FastAPI server to run via unicorn dockerfile.

```sh
FROM python:3.11-slim
SHELL ["/bin/bash", "-c"]

RUN apt-get update && \
    apt-get install -y --no-install-recommends build-essential \
    curl \
    apt-utils \
    gnupg2 &&\
    rm -rf /var/lib/apt/lists/* && \
    pip install --upgrade pip

RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -
RUN curl https://packages.microsoft.com/config/debian/11/prod.list > /etc/apt/sources.list.d/mssql-release.list

RUN apt-get update
RUN env ACCEPT_EULA=Y apt-get install -y msodbcsql18
WORKDIR /app
RUN pip install "datu-core[postgres,sqldb]"
ENTRYPOINT [] 
CMD ["uvicorn", "datu.main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
```

## Infrastructure

For running Datu application smoothly, make sure you are allocated about 1GB of CPU and 2GB of memory atleast.For configurable variables checkout the quickstart/configurations section.