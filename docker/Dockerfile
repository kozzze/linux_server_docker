# Stage 1: build deps
FROM python:3.11-slim AS builder

WORKDIR /app
COPY . .
RUN make install-dev
RUN make test

# Stage 2: runtime
FROM python:3.11-slim

WORKDIR /app
COPY --from=builder /app/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY ./src ./src

# IMPORTANT: порт должен быть 60080 (или тот, что выдали тебе)
CMD ["uvicorn", "src.main:app", "--host", "0.0.0.0", "--port", "60080"]