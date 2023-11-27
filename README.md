# django-todo
A simple todo app built with django

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git

$ pip install virtualenv   

$ virtualenv -p python3.7 env ---------- for virtual environment to run this project 

 to activate virual env ---- $ env\scripts\activate
```
You will need django to be installed in you computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ cd django-todo  
```

```bash
$ pip install django 
```

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

Cheers and Happy Coding :)


to create requirement file ----- pip freeze > requirements.txt


to push update ----

git checkout -b feature/deploy-app

git add .

git commit -m "Added Requirements" 

git push origin feature/deploy-app



on ec2 
```bash
$ nohup python manage.py runserver 0.0.0.0:8001
```

fordocker ---
vim Dockerfile ---------
```
FROM python:3
RUN pip install django==3.2
COPY . .
RUN python manage.py migrate
CMD ["python","manage.py","runserver","0.0.0.0:8001"]

```

sudo docker build . -t todo-app

sudo docker run -p 8001:8001 <imageID>
