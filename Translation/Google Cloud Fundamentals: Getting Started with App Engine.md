# Google Cloud Fundamentals: Getting Started with App Engine


### Initialize App Engine

Run the following code on your Terminal or Command Prompt with Cloud SDK installed.

* Run
```bash
gcloud auth login 
```
Then follow the prompts.

* To view your projects run
```bash
gcloud config list project
```

* Then set your project as default by running
```bash
gcloud config set project your-project-id
```
Replace 'your-project-id' with your project id you created

* To initialize your App Engine app with your project and choose its region run:
```bash
gcloud app create --project=your-project-id
```
replace 'your-project-id' with your chosen project id. When prompted select the region.

* Clone the source code repo for a sample hello_world directory:
```bash
git clone https://github.com/GoogleCloudPlatform/python-docs-samples
```
* Navigate to the source directory:
```bash
cd python-docs-samples/appengine/standard_python3/hello_world
```

### Deploy and run Hello World on App Engine

To deploy your app to App Engine Standard environment:

* Deploy your Hello World application
```bash
gcloud app deploy
```
If prompted press 
```bash
Y
```
and the press Enter. This app deploy command uses app.yaml file to identify project configuration.

* Launch your browser to view the app at http://YOUR_PROJECT_ID.appspot.com
```bash
gcloud app browse
```
copy and paste the URL in a browser window.
Congratulations! You created your application using App Engine.
