# Standalone Wordpress website hosted with Apache and automated with Terraform and Ansible

<h2>Project to deploy Wordpress website on AWS using terraform and ansible </h2> 

<h3>Prerequisite</h3>

 - Before launching Terraform template, aws cli should be installed and configured with proper access key and secret key

 - Terraform should be installed in your local machine

 - Ansible should be installed in your local machine. (NB: if running on Windows, WSL will be easiest option)

-  Configure AWS CLI with aws configure if you havent configured already

<h3>STEPS:</h3>

1. Clone this repo using command <code> git clone https://github.com/evannoelchi/wordpress-with-terraform-ansible.git</code>

2. Go to project folder <code> cd wordpress-with-terraform-ansible</code>

3. Initialize terraform <code>terraform init</code>

4. Location of shared_credentials_files, Change database and aws settings (if you prefer to use different region or AMI) in terraform.tfvars file

5. Generate Key pair using <code>ssh-keygen -f mykey-pair</code>

6. View Plan using <code>terraform plan -var-file="user.tfvars"</code>

7. Apply the plan using <code>terraform apply -var-file="user.tfvars"</code>

(After successfull provisioning of AWS Resources,Using remote-exec and private key, EC2 instance will be connected via SSH. Yum will be updated and Python will be installed so that local ansible server can communicate with the provisoned EC2 . Once Installation is done ,Using local exec , Ansible playbook will be run against provisioned EC2)

<h3>Everything is Automatic. This will provision all needed aws resources and also build and start webserver using Ansible</h3>

8. Destroy the resources <code>terraform destroy -var-file="user.tfvars"</code>

<h2>Thank you !!!!</h2> 
