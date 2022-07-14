FROM public.ecr.aws/lambda/python:3.6

COPY app.py requirements.txt ./

RUN python3.6 -m pip install -r requirements.txt -t .

ADD https://github.com/adieuadieu/serverless-chrome/releases/download/v1.0.0-41/stable-headless-chromium-amazonlinux-2017-03.zip /var/task/headless-chromium.zip

ADD https://chromedriver.storage.googleapis.com/2.37/chromedriver_linux64.zip /var/task/chromedriver.zip

RUN mkdir chromedriver

RUN mkdir headless-chromium

RUN unzip chromedriver.zip -d chromedriver

RUN unzip headless-chromium.zip -d headless-chromium

# Command can be overwritten by providing a different command in the template directly.
CMD ["app.lambda_handler"]
