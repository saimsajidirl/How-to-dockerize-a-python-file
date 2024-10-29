# commands for docker file of django

    FROM python:3.12.6

    WORKDIR /app

    COPY requirements.txt .

    RUN pip install -r requirements.txt

    COPY . .

    EXPOSE 5000

    CMD ["python", "manage.py", "runserver", "0.0.0.0:5000"]


# build and run the docker tile
    docker build -t myproject .


    docker run -p 5000:5000 --name myproject-container myproject
