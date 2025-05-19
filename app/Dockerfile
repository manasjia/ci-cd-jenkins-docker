
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

copy . . 

EXPOSE 80

CMD ["python", "main.py"]
