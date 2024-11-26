FROM python:3.10.5-alpine3.16
WORKDIR /app
COPY /api /app
RUN apk add --no-cache entr postgresql-dev musl-dev gcc
RUN pip install -r requirements.txt
EXPOSE 80
CMD ["gunicorn", "app:app", "-b", "0.0.0.0:8080", "--log-file", "-", "--access-logfile", "-", "--workers", "4", "--keep-alive", "0"]
