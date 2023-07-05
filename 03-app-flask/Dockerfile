# FROM ubuntu:22.04

# RUN apt update && apt install -y python3 python3-venv

FROM python:3.10

WORKDIR /app

RUN python3 -m venv .venv

# ENV VIRTUAL_ENV_BIN=/app/.venv/bin
ENV VIRTUAL_ENV=/app/.venv
ENV PATH="$VIRTUAL_ENV/bin:$PATH"
ENV FLASK_APP=src/app.py

COPY requirements.txt ./

# RUN $VIRTUAL_ENV_BIN/pip install -r requirements.txt
RUN pip install -r requirements.txt

COPY . .

EXPOSE 5000

# CMD $VIRTUAL_ENV_BIN/flask --app src/app.py run --host 0.0.0.0 
# CMD flask --app src/app.py run --host 0.0.0.0 
CMD flask run --host 0.0.0.0 