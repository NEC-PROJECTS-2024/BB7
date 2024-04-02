FROM ubuntu

RUN apt update
RUN apt install python3-pip -y
RUN pip3 install Flask
RUN pip3 install tensorflow
RUN pip3 install pillow


# Set the working directory in the container
WORKDIR /app

# Copy the entire application (including the webapp directory) to /app
COPY . /app

# Ensure that Flask knows where to find the application
# Assuming setup.py is directly under webapp/ and defines the app
ENV FLASK_APP=webapp/setup.py

# Expose the port the app runs on
EXPOSE 8000
ENV FLASK_RUN_HOST=0.0.0.0
# Command to run the app
CMD ["python3", "-m", "flask", "run", "--host=0.0.0.0"]
