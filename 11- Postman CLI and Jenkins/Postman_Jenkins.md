# Postman CLI and Jenkins CI/CD Pipeline Setup

## 1. Install Postman CLI
Follow the instructions for installing the Postman CLI on your system:  
[Postman CLI Installation - Windows](https://learning.postman.com/docs/postman-cli/postman-cli-installation/#windows-installation)

## 2. Generate Postman API Key
Follow the instructions to generate your API key:  
[Generate a Postman API Key](https://learning.postman.com/docs/developer/postman-api/authentication/#generate-a-postman-api-key)

## 3. Run Postman Collection Using Postman CLI
   1. **Login to Postman**:  
   ```bash
   postman login --with-api-key {Place Your API-Key Here}
   2. **Run the Collection**:
   ```bash 
    postman collection run {Place Your Collection ID Here} -d {Place Your Data File Here} -g {Place Your Global Variables Here (If Any)} -r html

_________________________________________________________________________________________________

# Jenkins CI/CD Pipeline Configuration

## 1. Run Collection From Postman
    1- Select "Automate runs via CLI".
    2- Click "Configure command" under "Run on CI/CD".

## 2. Generate Postman CLI Configuration
    1- Collection: Select the collection you need to run.
    2- CI/CD Provider: Select "Jenkins".
    3- Operating System for CI/CD: Select "your operating system".

## 3. Copy the Postman CLI Command
    Copy the command generated for your configuration.

## 4. Run Jenkins on Your Local Machine
    1- Open the command prompt where your jenkins.war file is located.
    2- Run this command:
    java -jar jenkins.war        
        Note: Don't close the command prompt terminal.
    3- Open any browser and log in to Jenkins through this URL:
        http://localhost:8080/

## 5. Create a New Job
    1- Select "New Item".
    2- Select "Pipeline".

## 6. Adding Local Node.js Installation to Jenkins
    1- Go to Jenkins "Dashboard" -> "Manage Jenkins" -> "Tools".
    2- Scroll down to the section "NodeJS installations".
    3- Add Node.js.
    4- Uncheck "Install automatically".
    5- Add a name (you will use it in your script).
    6- Add your local Node.js installation directory:
        C:\Program Files\nodejs
        Note: If you don't find it, please install it first.

    If Nodejs isn't installed on your local machine, you can select "Install automatically", and it will be installed on Jenkins.

## 7. Paste the Command Copied in Step 3 Into the Pipeline Script
    1- Apply & Save.
    2- Replace the Node.js variable with your Node.js name on Jenkins.
    3- Replace the API key with your Postman API key in the stage "Postman CLI Login".
    4- Modify the script in the stage "Running Collection" to meet your requirements.
    5- Apply & Save.

## 8. Run the Pipeline
    Go to "Build Now" to run the pipeline.

