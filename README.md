# django-for-google-app-engine
Deploying your first Django project on Google App Engine may be easier than you think.

Documentation and tutorials cover many of the skills needed and the steps to build and deploy secure, advanced web applications. 

### There are two related "getting started" tutorials ###

In Django documentation there is a two-part exercise where you firstly generate a project **mysite** and later add an app **polls** within that project.

In Google documentation there is a series of steps laid out to modify the **mysite** project with the app **polls** you created by completing the Django tutorial. It describes the extra steps required to add Google cloud services to the sample project before deploying and running it on the *Google App Engine (GAE) standard environment for Python*.

If an error occurs when the completed project and app is deployed to the GAE it may be quite difficult to find the mistake or misunderstanding that results in error messages. 

Just a simple misunderstanding can result in countless hours spent on trying to understand a variety of errors that can occur. For instance, placing the project's **requirements.txt** file in the wrong folder can cause a variety of errors that can be quite opaque to someone using Google App Engine for the first time. 

A google search for a few errors shows these are commonly encountered by people in their first efforts to deploy Django applications to Google App Engine. 

There are no consistent explanations or solutions to these common questions, and it is possible that a number of the people encountering errors eventually gave up.

See for example Google Search results for the queries: 

- ModuleNotFoundError: No module named 'main'
- django app engine 502 bad gateway
- django ModuleNotFoundError: No module named 'gunicorn'
- ModuleNotFoundError: No module named 'django'

This repository contains the code generated in part 1 of the Django getting started guide (project **mysite**) and the necessary changes to that project (without the app ***polls***) so that it can be deployed and run on Google App Engine. Doing only part of the tutorials leaves relatively little scope for errors. This means that if something is not working correctly, there is less work to review to find the cause of any errors. 

When this part of the introduction to Django on Google App Engine is working, the additional steps in the Django and Google tutorials can be added and tested incrementally. 

For instance, adding the Secrets Manager and serving static files can be added and tested before incorporating Google database support. Checking each functional piece before moving on to the next helps to reduce the chance of mistakes, and also reduces the amount of work to review to find the cause of any errors. 

Developing Django projects for Google App engine - Software tools and skills to get started: 
1. Installation of python. 
   - See for example **Beginner's Guide to Python** 
            at https://wiki.python.org/moin/BeginnersGuide 
2. Installation of an integrated development environment such as **Visual Studio Code**. 
   - See for example **Django Tutorial in Visual Studio Code** 
            at https://code.visualstudio.com/docs/python/tutorial-django#_create-a-project-environment-for-the-django-tutorial         
3. Understanding Python virtual environments, installing Django in a virtual environment, and using a ***requirements.txt** file.
   - See for example **Generating a requirements.txt file | Django tips**
            at https://www.youtube.com/watch?v=20ALbJTB4Bo 
4. Generating the first python modules for a Django project. 
   - See the example **Writing your first Django app, part 1** 
            at https://docs.djangoproject.com/en/4.2/intro/tutorial01/ 
5. Google App Engine, standard environment, for deploying a Django project. 
   - See the tutorial **Running Django on the App Engine standard environment** 
            at https://cloud.google.com/python/django/appengine#gcloud_2 
6. Adjustments to the first python modules for a Django project so they can be deployed to Google App Engine standard environment.

A Django project with a requirements.txt file able to be started in the development environment was created by the commands shown in the command log file: 
**[command-log-Django-tutorial.md](command-log-Django-tutorial.md)**.

Visual Studio Code can be used to edit the Django project created with the commands shown. 

Note that though it might seem reasonable to open the folder **mysite** with Visual Studio Code, it works better to open the parent folder - the folder that contains both the project folder **mysite** and the virtual environment folder **.venv**. 
![Django-opening-with-VS-Code](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/e5a3046c-1b20-4e4e-abf4-34e29e684b0f)
After opening the parent folder, Visual Studio Code can expand the sub-directories, listing the files within **mysite** and also shows that the virtual environment folder **.venv** is in the same parent folder as the project.
![Django-open-in-VSCode-3](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/4ba03058-d327-41b6-aeb4-a70419c45bc5)
The above screen image is the top-left corner of the Visual Studio Code application.

The following image is the entire screen image. Notice some parts of the screen -  
+ On the left list of folders and files, the file **requirements.txt** has been selected. This opens the file for editing. The top-right of the screen is the contents of the file. 
+ The contents of the **requirements.txt** have been changed, adding the Python libraries needed to deploy the project to the Google App Engine. 
+ On the bottom-right of that window containing the **requirements.txt** file, Visual Studio Code displays a button labelled ***Create Environment...***. Selecting this button leads to a few options being displayed with which to rebuild the **.venv** virtual environment folder. This is useful if changes have been made to list of libraries required for the project. Visual Studio Code by default creates/recreates the virtual environemt in a folder named **.venv** regardless of what name you chose for creating the virtual environment when you created the project. 
+ The bottom-right of the screen image is a command console - opened by selcting the **terminal** menu at the top of the screen. The command console shows that Visual Studio Code has activated the virtual environment - after rebuilding the virtual environement folder. Then a command was entered to run the project on the local development server. 
![Django-generated-project-for-GAE-runserver](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/c91ccddf-5058-4089-aea1-b432b92e24f5)

To ensure the project can be deployed and started in Google App Engine standard environment, some changes are made to two of the generated files: 
1. The ***requirements.txt*** file, and
2. The ***settings.py*** file. 

and two files need to be added to the Django project in the same sub-directory as the file ***manage.py***:
1. A file ***main.py***, and
2. A file ***app.yaml***

The ***main.py*** and ***app.yaml*** files are described in the Google App Engine tutorial referred to at paragraph 5 above. 

The contents are copied from: 
- https://github.com/GoogleCloudPlatform/python-docs-samples/blob/fcc6242324310150e5d66f08aec7d55ff4b6c867/appengine/standard_python3/django/main.py 
and 
- https://github.com/GoogleCloudPlatform/python-docs-samples/blob/HEAD/appengine/standard_python3/django/app.yaml 

The file ***settings.py*** which is generated by the command that created the Django project files contains an environment variable **SECRET_KEY** that needs to be stored securely. 

This requirement is addressed in one of the later steps using Google's Secrets Manager and may be left unchanged for this preliminary deployment and checking that the project will run. 

The few changes above (some minor code changes in two files and adding two new files) are the ***only*** changes needed to allow the generated Django project to be deployed and run in Google App Engine. 

### Now to verify that the project will run in the Google App Engine ###
Just a few of the steps in the Google documentation ***Running Django on the App Engine standard environment*** at https://cloud.google.com/python/django/appengine#gcloud_2 are required: 
1.  The first 3 steps under the heading "Before you begin"
    + In the Google Cloud console, on the project selector page, select or create a Google Cloud project.
    + Make sure that billing is enabled for your Google Cloud project.
    + Enable the Cloud SQL Admin API, Secret Manager, and Cloud Build APIs.
2.  The last 3 steps under the heading **Run the app on your local computer** -
    + Start the Django web server: `python manage.py runserver`
    + In your browser, go to ``http://localhost:8080``
    + The Django tutorial project displays an introductory web page to confirm that it is running successfully - 
      ![Django-generated-project](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/20d77a26-a7f6-4f6c-9a27-71f313292dd0)
    + Press Ctrl+C to stop the local web server.
3.  Use the gcloud CLI in the Google Cloud console to upload the Django project. 
    + [Steps for uploading the Django project to the Google Cloud, ready to be deployed](Upload-project-with-Google-Cloud-Console.md).
4.  Deploy the project as shown in steps 1 to 5 under the heading **Deploy the app to the App Engine standard environment** - except that: 
    + After editing the ***app.yaml*** file to include the value of the environment variable *APPENGINE_URL* (the value is generated when the project is first run in the GAE), delete the destination directory with the uploaded files, then upload the entire source directory again. Otherwise the original **app.yaml** file will be kept and a new file with a version number is created, which isn't what is wanted.
    + Note that the Google document says "upload the app by running the command ``gcloud app deploy`` which deploys the app". 
    + The instructions above describe "uploading" the project as the process of copying you project from a local development computer into the Google Cloud Console. The command ''gcloud app deploy`` is run after the projected is uploaded to deploy it in the Google App Engine. 
    + If everything works correctly, the deployed incomplete app will display the same "confirmation" screen in the Google App Engine that it displays in the local development server - 
![Django-generated-project-upload-for-deployed-OK](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/11c17cfa-cc4c-4ed7-a8b7-3020faed5b27)

This is enough of the steps in the Google documentation **Running Django on the App Engine standard environment** to make sure you can deploy and run part of a Django project with a minimum of steps - and a reduced scope to explore if any error does happen. 

The additional steps to complete the sample project can then be carried out and tested one by one, resuming at 
**Creating the Polls app** in **Writing your first Django app, part 1** at https://docs.djangoproject.com/en/4.2/intro/tutorial01/ 

Then continue with the further steps in **Running Django on the App Engine standard environment** at https://cloud.google.com/python/django/appengine#gcloud_2. These steps include using Google's Secrets Manager and adding database services to the project. 
