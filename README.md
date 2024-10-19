
    # Base image
    FROM python:3.12.6

    # Work directory
    WORKDIR /app

    # Copy requirements.txt
    COPY requirements.txt .

    # Install dependencies
    RUN pip install -r requirements.txt

    # Copy project files
    COPY . .

    # Expose port
    EXPOSE 5000

    # Command to run the Django server
    CMD ["python", "manage.py", "runserver", "0.0.0.0:5000"]



    # build the dockerfile
    docker build -t myproject .


    # run dockerfile
    docker run -p 5000:5000 --name myproject-container myproject
