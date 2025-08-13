FROM python:3.9 

WORKDIR /app

COPY . .

RUN pip install uvicorn fastapi

EXPOSE 8080

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8080"]