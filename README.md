# Deploy steps
## Build image
```sh
gcloud builds submit --tag gcr.io/utbeast/utb-cms:v1
```
## Deploy image
```
gcloud beta run deploy utb-cms --image gcr.io/utbeast/utb-cms:v1 \
  --platform managed \
  --add-cloudsql-instances mysql-db \
  --update-env-vars DB_HOST='127.0.0.1',DB_NAME=wordpress,DB_USER=wordpress,DB_PASSWORD=8ELHns62aPh25dpe,CLOUDSQL_INSTANCE='utbeast:europe-west1:mysql-db'
```
