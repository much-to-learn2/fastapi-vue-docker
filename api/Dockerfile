FROM python:3.10.4-slim-buster

WORKDIR /app

COPY ./api ./api
COPY ./requirements.txt .

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

EXPOSE 8000
CMD ["uvicorn", "api.app:app", "--host", "0.0.0.0", "--port", "8000", "--root-path", "/api"]
