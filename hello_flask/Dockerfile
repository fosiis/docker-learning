FROM python:3.8-slim
WORKDIR /app
COPY . .
#RUN what this container needs to install, tasks it needs to achieve, and dependencies 
RUN apt-get update && apt-get install -y \
    gcc \
    default-libmysqlclient-dev \
    pkg-config \
    && pip install flask mysqlclient \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
#this port available so that we can access the container from a localhost. This makes the application accessible from outside the container.
EXPOSE 5002
CMD [ "python", "app.py" ]
