FROM python:3.11-alpine

RUN apk update && apk upgrade


WORKDIR /app
COPY . .
RUN pip install .
RUN pip install pytest>=6.2.5
RUN pip install pytest-asyncio==0.25.3
RUN pip install httpx==0.28.1



#CMD ["uvicorn", "src.main:app", "--host", "0.0.0.0", "--port", "60080"]
#CMD pytest tests
