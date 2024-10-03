**# Graded Project on Building CI-CD Pipeline Tool**

Create a complete CI-CD pipeline using bash, python, and crontabs. The list of tasks is specified below: 

**Steps**
  1. "**CICDProjectPipeline**" repository is created in Github
  2. Added **index.html** file to the repository
  3. Open PowerShell in admin mode and type wsl
  4. Installed Nginx in local linux instance using
     sudo apt update
     sudo apt install nginx
  5. Staredt the Nginx using
     sudo systemctl start nginx
  6. Opened the browser and navigate to **http://localhost** to see the Nginx welcome page running
  7. Installed Python
     sudo apt install python3-pip -y
     pip3 install requests
  8. Installed git
     sudo apt install git -y
  10. Created a folder named "PipelineRepo" to store your scripts and clone github repo
     mkdir PipelineRepo
     cd PipelineRepo
  11. Created a python script "checkPipelineChanges.py" and write the script to fetch and check the latest commits from Github repository using GithubAPI.
     Once fetched, the script should store the last commit and verify the new commits coming in. If both doesn't match, then it should return true
  12. Created a bash script "deployChanges.sh" to fetch the latest code from Github, deploys into nginx and restarts the nginx service
  13. Created a wrapper script "wrapperScript.sh" to integrate both "checkPipelineChanges.py" & "deployChanges.sh". This script checks if the "checkPipelineChanges.py" scripts returns true and then invokes "deployChanges.sh" to deploy code
  14. Given both the bash scripts execution permissions
      chmod +x deployChanges.sh
      chmod +x wrapperScript.sh
  15. Setup a cron job to run the "wrapper.sh" script every 1 minute
      type "crontab -e"
      It will prompt to choose an editor vi or nano etc. Select as per your expertise
      Add the below line and save
      */1 * * * * /usr/bin/python3 /path/to/check_commits.py && /path/to/deploy.sh
  16. To test the script, updated the index.html in the repository and navigated to **http://localhost** to verify the changes are reflecting
     
