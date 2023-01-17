FROM golang:1.15.8-buster

COPY . /app

RUN make /app

CMD ["python", "/app/app.py"]
