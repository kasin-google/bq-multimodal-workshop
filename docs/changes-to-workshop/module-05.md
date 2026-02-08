# 5. Create a storage bucket
Create a Cloud Storage Bucket and copy the available media to your own bucket. You will use this to store available media for our wonderful pets. You will also create a connection to access the bucket through BigQuery.

Paste and execute the following in the terminal:

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

> [!NOTE]
> 🐱 If you want to add a picture of your own pet, this is your chance. You will need to modify the code along this codelab if you do. Upload a profile picture onto your bucket in JPG or PNG. You can add videos and more pictures in the additional_media folder. Make sure the bucket you are using is secure and can only be accessed by people you want to see the pictures and videos.

> [!NOTE]
> 💡 Take note of the name of your bucket (i.e., <<YOUR_PROJECT_ID>>-petverse).


