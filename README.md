# build-env-jenkins-Terraform
Network infrastructure with Jenkins and Web on AWS 

git clone https://github.com/NAzebiah/build-env-jenkins-terraform.git

In the main.tf file replace xxxx and set the location of your aws credentials file like this shared_credentials_file = "C:\Users\xxxx\.aws"

In terraform.tfvars set the correct key for your profile 

cd terraform/

terraform init
terraform plan
terraform apply -auto-approve

This will create the network infrastructure, jenkins server and a dev web server 

Once your Jenkins server has initialised you can access on port http:xxxxxx:8080
Connect to your Jenkins server via ssh and run this command to get the admin password sudo cat /var/lib/jenkins/secrets/initialAdminPassword

jenkins scipt image 

Jenkins server
The provisioning of the Jenkins server and installation of plugins is automated in the compute.tf by calling install_jenkins.sh
This installs Java, Mavn, Git, Jenkins, SSH and configures the git plugins 

Web server 
The provisioning of the webserver is automated in the compute.tf by calling install_httpd.sh this set up the webserver elements and puts a test html page up for you to view
