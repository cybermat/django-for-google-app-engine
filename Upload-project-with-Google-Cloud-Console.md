### Uploading a Django Project via the Google Cloud Console
After uploading the project it may be deployed and tested in the Google App Engine standard environment for Python. 
AFter opening the Google Cloud Console, open a cloud shell terminal, create a directory to upload your project into, then select the "upload" to Google Cloud option.
![Django-generated-project-upload-for-deployment](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/90772518-a666-4d9f-bb10-3d75b4b714f7)
There are a number of screens in which you select the directory to upload from, and the destination directory for the files to be uploaded.
![Django-generated-project-upload-for-deployment-dest](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/03e175a8-afb8-48e1-ae0b-7816614a2048)
The "folder" icon allows you to select the directory created previously as the destination.
![Django-generated-project-upload-for-deployment-dest2](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/4453a697-a82c-4bda-b327-5959c1ed854f)
Choosing the folder to upload your project from allows you to navigate your local directory to the folder with your project. Do not upload the environment folder **.venv**. 
Google App Engine creates the environment for the project when deploying it - adding libraries that are listed in the **requirments.txt** file uploaded with your project.
![Django-generated-project-upload-for-deployment-dest3](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/4d15f71a-665c-47b4-a3a0-70ed47671e89)
After selecting the source directory, a list of files that will be uploaded being displayed. Selecting the "upload" option on the bottom-right results in the files being upload.
![Django-generated-project-upload-for-deployment-dest4](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/941a3e63-3e78-4f6f-8357-90fe72606f75)
The successful progress of the file uploading is displayed with green ticks being added on completion next to the name of each uploaded file. 
![Django-generated-project-upload-for-deployment-dest5](https://github.com/cybermat/django-for-google-app-engine/assets/2298091/664acde5-0915-4098-a6f9-a1934caab8ce)


