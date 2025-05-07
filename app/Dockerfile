# Introduce an invalid base image to simulate failure
FROM invalid-base-image

WORKDIR /app
COPY app.py .

RUN pip install flask

CMD ["python", "app.py"]
