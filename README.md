# Gcloud console CLI
1. gcloud auth list - show all auth profiles
2. gcloud config configurations list - list all defined configurations
3. gcloud config configurations activate chladic - activate chladic configuration
4. gcloud config set account chladic@email.com - set chladic@gmail.com auth for active configuration
5. gcloud config list - show properties of current active configuration
6. gcloud config set project chladic - Set project for active configuration

# Billing
1. Billing account can cover multiple projects
2. Billing export must be done per each billing account
3. Billing export is not real time with hours delay
4. Budget can be set either to billing account or to project
5. Controlling billing account for project has nothing to do with controlling project

# Google cloud shell
1. 5GB persistant storage
2. Preinstalled tools, gcloud, kubectl, docker, vim ...
3. Web preview of apps running 

# Google storage
1. By default public access is forbidden
2. Bucket can have uniform policy for everything inside, or fine-grained using ACL per each object
3. You can set bucket that requestor pays whenever wants to read from it
4. Example of renaming object: gsutil mv -p gs://object1 gs://object2
5. Classes: Standard, Nearline(for backup - 30 days), Coldline (90 days, Disaster recovery data), Archive (regulation archives, 1 year)
