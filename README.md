# Sample Django Project on Docker

- [Docker-Django Tutorial Reference](https://www.youtube.com/watch?v=KaSJMDo-aPs)
- [Other Docker-Django Tutorials](./docker-django_tutorials_evaluation.md)

```shell
touch Dockerfile
```

```dockerfile
# Base Image
FROM python:3.6

# create and set working directory
RUN mkdir /app
WORKDIR /app

# Add current directory code to working directory
ADD . /app/

# set default environment variables
ENV PYTHONUNBUFFERED 1
ENV LANG C.UTF-8
ENV DEBIAN_FRONTEND=noninteractive 

# set project environment variables
# grab these via Python's os.environ
# these are 100% optional here
ENV PORT=8888

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
        tzdata \
        python3-setuptools \
        python3-pip \
        python3-dev \
        python3-venv \
        git \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*


# install environment dependencies
RUN pip3 install --upgrade pip 
RUN pip3 install pipenv

# Install project dependencies
RUN pipenv install --skip-lock --system --dev

EXPOSE 8888
CMD gunicorn cfehome.wsgi:application --bind 0.0.0.0:$PORT
```

```shell
docker login
docker run -it -p 80:8888 <image-name>
```

Check <image-name> with 

```shell
docker images
```

Now it runs on http://localhost/

### Additional Docker commands

```shell
docker ps -a
docker images
docker image rm [OPTIONS like -f] <image-sha>
```



### Deploying it to AWS EC2 using Beanstalk

[AWS beanstalk dockerizing documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/single-container-docker.html)	

```
pip install awsebcli --upgrade
eb init 
eb local run --port 5000
```

```shell
git add .
git commit -m "commit message"
eb deploy
eb open
```



