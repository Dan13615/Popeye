FROM python:3.13-rc-alpine

WORKDIR /app
COPY . .
RUN pip3 install -r requirements.txt
EXPOSE 80
CMD flask run --host=0.0.0.0 --port=80
