# Lab: Google Cloud Fundamentals: Getting Started with App Engine 

## Objectives

    - Initialize App Engine.

    - Preview an App Engine application running locally.

    - Deploy an App Engine application, so that others can reach it.

    - Disable an App Engine application, when you no longer want it to be visible.


## Steps


### Initialize App Engine

1. Initialize your App Engine app with your project and choose its region

        gcloud app create --project=$DEVSHELL_PROJECT_ID
        (When prompted, select the region where you want your App Engine application located.)

2. Clone the source code repository for a sample application in the hello_world directory

        git clone https://github.com/GoogleCloudPlatform/python-docs-samples

3. Navigate to the source directory:

        cd python-docs-samples/appengine/standard_python3/hello_world


### Run Hello World application locally

4. Execute the following command to download and update the packages list.

        sudo apt-get update

5. Set up a virtual environment in which you will run your application.

        sudo apt-get install virtualenv
        (If prompted [Y/n], press Y and then Enter)

        virtualenv -p python3 venv

6. Activate the virtual environment.

        source venv/bin/activate

7. Navigate to your project directory and install dependencies.

        pip install  -r requirements.txt

8. Run the application:

        python main.py
 
9. Web preview 

        https://ssh.cloud.google.com/devshell/proxy?authuser=0&port=8080&environment_id=default
            Result: Hello World displayed in browser

10. End the test / abort the deployed service.

        Ctrl+C 

11. Verify the app is not deployed

        - Refresh browser        
            Result: Browser displays: "Couldn't connect to a server on port 8080" or "400. That's an error"


### Deploy and run Hello World on App Engine

    (deploy your application to the App Engine Standard environment)

12. Navigate to the source directory:

        cd ~/python-docs-samples/appengine/standard_python3/hello_world

13. Deploy your Hello World application.

        gcloud app deploy
        (If prompted "Do you want to continue (Y/n)?", press Y and then Enter)
        Note: This app deploy command uses the app.yaml file to identify project configuration

14. Launch browser to view the app

        gcloud app browse

        - Use url generated by this command to paste into web browser
            Result: (http://YOUR_PROJECT_ID.appspot.com) displays "Hello World!"


### Disable the application

15. Click Disable application

    //HOW TO DO THIS!!

16. Confirm App disabled

    - Refresh browser
      Result: should be a 404 error

## Congratulations!
You created your first application using App Engine!