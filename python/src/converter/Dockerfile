# FROM python:3.12.2-slim-bullseye

# RUN apt-get update \
#     && apt-get install -y --no-install-recommends --no-install-suggests \
#     build-essential ffmpeg \
#     && pip install --no-cache-dir --upgrade pip

# WORKDIR /app
# COPY ./requirements.txt /app
# RUN pip install --no-cache-dir --requirement /app/requirements.txt
# COPY . /app

# CMD ["python3", "consumer.py"]
FROM python:3.12.2-slim-bullseye

RUN apt-get update \
    && apt-get install -y --no-install-recommends --no-install-suggests \
    build-essential \
    ffmpeg \
    pkg-config \
    default-libmysqlclient-dev \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir --upgrade pip

WORKDIR /app
COPY ./requirements.txt /app
RUN pip install --no-cache-dir --requirement /app/requirements.txt
COPY . /app

CMD ["python3", "consumer.py"]
