FROM python:3.7-alpine

RUN mkdir /flaskapp
WORKDIR /flaskapp
ADD . /flaskapp/
RUN pip install -r /flaskapp/requirements.txt

EXPOSE 5555
CMD ["python", "/flaskapp/flask_app.py"]
