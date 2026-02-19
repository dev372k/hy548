FROM python:3.13.2-bookworm

ENV PYTHONUNBUFFERED=1
ENV DJANGO_DEBUG=1

WORKDIR /app

# Install vim-tiny
RUN apt-get update && \
    apt-get install -y vim-tiny && \
    rm -rf /var/lib/apt/lists/*

# Copy project
COPY . /app

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Create volume for database
VOLUME /app/db

EXPOSE 8000

CMD ["./start.sh"]