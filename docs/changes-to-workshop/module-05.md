```
~/petverse-setup.sh
cd ~/
export REGION=asia-southeast3
gcloud storage buckets create gs://$DEVSHELL_PROJECT_ID-petverse --uniform-bucket-level-access --location=$REGION
gcloud storage cp -r gs://sample-data-and-media/petverse/* gs://$DEVSHELL_PROJECT_ID-petverse/
bq mk --dataset --location=$REGION --project_id=$DEVSHELL_PROJECT_ID petverse
bq mk --connection --location=$REGION --project_id=$DEVSHELL_PROJECT_ID \
--connection_type=CLOUD_RESOURCE pet-connection
echo "your bucket is gs://$DEVSHELL_PROJECT_ID-petverse "
```