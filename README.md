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

Now that the dependences are installed, you have to install the local dependencies in your virtual environment.

To do this, in your terminal type the following;

```
$ source env/bin/activate
$ pip install -r requirements.txt
```

##### Initialize your local PostgreSQL database

Open a new terminal window and run this command;

```
$ ./initializeLocalDB.sh
```

Make sure that after you run this command, to open up the file. I have commented out commands that can't run directly from a bash script, but you need to run them to create your local database 'mobile_dev_api' or else when you try to setupdb.sh it will complain that there is no database to create tables in

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
$ http://localhost:5000/first_names
```

It should output a list of JSON names from your database


##### Setting up your Heroku Server

Go to heroku.com and create a new user (very easy and quick)

Click 'Create New App' and select a name for your App

Once made, navigate in your tabs to 'Deploy' and select 'Connect to GitHub'.

GitHub is where you will store all of the changes to your files and push them from your personal machine, so you will want to push from GitHub to Heroku when you want. That way everything stays uniform as you like it.

Wherever you put this pulled template, put that as the repo to connect to.

Now in your project directory, type in the following code (replacing the name with your app name) to connect your github project to Heroku

```
$ heroku git:remote -a <Name of your App>
```

If it worked correctly you should see 

```
$ set git remote heroku to https://git.heroku.com/<name-of-your-app>.git
```

Then to push to the app, type in the following;

```
$ git push heroku master
```

Now return to your Heroku app on your browser and select the tab 'Resources'.

Click on the Add-On that should have created itself called 

'Heroku Postgres :: Database'

Then select settings from the tab bar, and view your database credentials.

Copy and paste the URI given into the config.env file as the value for DATABASE_URL='yourinfo'

Change the flask configuration to 'production'

Then run './setupdb.sh' and instead of running on your local environment, it will create the new tables in your Heroku Database. To check, go back to your browser and see that 4 tables were created.

In later stages of production, it is vital to migrate your database data so you won't lose user information in the process. To learn more about that see Flask Migrate in this link:

https://flask-migrate.readthedocs.io/en/latest/





