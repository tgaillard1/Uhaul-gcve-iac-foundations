# U-Haul POC Private Cloud

## Private Cloud Deployment

Follow the steps below:
 * Log into your [Google Cloud Console](https://accounts.google.com/) (GCP)
 * Open Cloud Shell (select the square icon <img src="https://github.com/tgaillard1/Uhaul-gcve-iac-foundations/blob/main/docs/cloud-shell.png" alt="Cloud Shell Icon"/> in the top right of the console)
 * Validate what project you are in on GCP.  Existing projects for U-Haul are --> api-project-710821853829 and u-haul-6c268.  If needed run this command to change to one of those projects, e.g., --> gcloud config set project api-project-710821853829
   
     * Clone git directory into the cloud shell
    
        ```
        git clone https://github.com/tgaillard1/Uhaul-gcve-iac-foundations.git
        ```
     * Change directories to the --> project-create stage
    
        ```
        cd ~/Uhaul-gcve-iac-foundations/stages/01-privatecloud/project-create/
        ```
     * Copy --> terraform.tfvars.example to --> terraform.tfvars
    
        ```
        cp terraform.tfvars.example terraform.tfvars
        ```
     * Change the variables in the --> terraform.tfvars file
    
        ```
        vi terraform.tfvars
        ```
     * Enable the GCP API's to perform the terraform actions
    
        ```
        gcloud services enable \
        compute.googleapis.com \
        iam.googleapis.com \
        cloudresourcemanager.googleapis.com \
        iamcredentials.googleapis.com \
        monitoring.googleapis.com \
        logging.googleapis.com \
        serviceusage.googleapis.com \
        cloudbilling.googleapis.com \
        vmwareengine.googleapis.com
        ```
     * Execture the following terraform commands to initiate the deployment
    
        ```
        terraform init
        ```
        ```
        terraform plan
        ```
        ```
        terraform apply
        ```

## Next steps

 * Proceed to the second module --> [01a-privatecloud](../01a-privatecloud).


