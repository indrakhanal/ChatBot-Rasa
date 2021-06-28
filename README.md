Install all requirement from requirement.txt
- after sucessfully installing all package use command as:
- rasa init ## to start rasa project with required files
- rasa train ## to train the rasa model
- rasa shell ## to test the model in command line interface

## Run on local machine
#### Without docker
In terminal(Command Line)
```
rasa run -m models --endpoints /endpoints/endpoints.yml
```
or
```
rasa run -m models --enable-api --endpoints /endpoints/endpoints.yml --cors "*"
```
In another Terminal
```
rasa run actions   
```

For Deployment:
## Deploy on heroku using Docker as:

1. run docker desktop on windows
2. docker login
3. docker build -t <image-name> .

## After building docker image add project to the git and push it to the heroku master 
1. git add .
2. git commit -m "your message"
3. heroku login
4. heroku container:login ## heroku app should be install in your system
5. heroku create <your heroku app name> ## eg: my-app the app name should be available to heroku or you can manually create from heroku.com from your verified account
6. docker tag <image-name> registry.heroku.com/<app-name>/web
7. docker push registry.heroku.com/<app-name>/web
8. heroku container:release web --app=<app-name>

## the project will deployed on heroku you can check as:
https://<app-name>.herokuapp.com