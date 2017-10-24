# Flask-PostgreSQL-Heroku API on a Mac

## Setting up

##### Clone the repo

```
$ git clone git@github.com:jfairf01/Flask-PostgreSQL-Heroku-API.git
```

##### Install All Dependencies

To install the dependencies, run the following command;

```
$ ./installDependencies.sh
```

##### Initialize your local PostgreSQL database

Open a new terminal window and run this command;

```
$ ./initializeLocalDB.sh
```


##### Initialize your database with fake data

In the main directory run the following;

```
$ ./setupdb.sh
```

##### Running the app

```
$ ./startApp.sh
```

Each file holds comments describing what the dependencies are;

If your system does not run them, look online to find the alternative method of running them on your system.


To see if your app works, once you start it open a browser and type in the following URL;

```
http://localhost:5000/first_names
```

It should output a list of JSON names from your database


##### Setting up your Heroku Server

Go to heroku.com and create a new user (very easy and quick)

Click 'Create New App' and select a name for your App

Once made, navigate in your tabs to 'Deploy' and select 'Connect to GitHub'.

GitHub is where you will store all of the changes to your files and push them from your personal machine, so you will want to push from GitHub to Heroku when you want. That way everything stays uniform as you like it.

Wherever you put this pulled template, put that as the repo to connect to.




