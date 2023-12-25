FROM python:3.10-slim-buster

# Inside Container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# this contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# install the Python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
# . means everyhting in current directory 
# first period . -/backend-flask (outside container)
# second period . / backend-flask (inside container)
COPY . .

# Set Environment Variables (Env Vars)
# Inside Container and will remain set whent he container is running
ENV FLASK_ENV=development

#
EXPOSE ${PORT}

# CMD (command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]