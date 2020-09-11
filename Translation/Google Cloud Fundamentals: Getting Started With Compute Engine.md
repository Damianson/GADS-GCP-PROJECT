# Google Cloud Fundamentals: Getting Started With Compute Engine


### Create a virtual machine using the command line

To Create a VM in GCP run the following code on your Terminal or Command Prompt with Cloud SDK installed.

* Run
```bash
gcloud auth login 
```
Then follow the prompts.

* Then set your project as default by running
```bash
gcloud config set project your-project-id
```
Replace 'your-project-id' with your project id you created

* To create your vm run
```bash
gcloud compute instances create your-instance-name --zone my-zone
```
Replace 'your-instance-name' with the name you want to give your VM and replace 'my-zone' with your specified zone name.

* To test your connection run:
```bash
gcloud compute ssh --zone my-zone your-instance-name
```
to exit the ssh just run
```
exit
```
Congratulations you've created your VM.
