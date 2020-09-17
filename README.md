# PrimesLab
Pruebas de CMS en DIVIO

# Run the app locally


1. Prepare Procfile
Unix-like
web: gunicorn gettingstarted.wsgi --log-file -

Windows:
web: python manage.py runserver 0.0.0.0:5000

2. Active virtual env
    $cd env/Scrips
    $./activate

3. Build Pack
    $heroku buildpacks:add heroku/python -a primeslab --index=1

4. Scale the app
Right now, your app is running on a single web dyno. 
   $heroku ps
Scale the number of web dynos to one:
   $heroku ps:scale web=1 -a primeslab -f Procfile.windows

#Note: At free account, the max of availables dynos is 1.

5. Collect Statics files
    $python manage.py collectstatic

5. Load heroku web 
    In Windows> $heroku local web -f Procfile.windows
    In Unix-like: heroku local web 

# Deploy in Heroku cloud

1. Create remote in local repository
    $git remote heroku 
2. Deploying code
    $git push heroku master

