# GCP Cheatsheet

---

## 1. gcloud CLI Basics
- Authenticate: `gcloud auth login`
- Set project: `gcloud config set project PROJECT_ID`
- List resources: `gcloud compute instances list`, `gcloud iam roles list`

---

## 2. Compute
- Create VM: `gcloud compute instances create NAME --zone=ZONE --machine-type=e2-medium`
- SSH: `gcloud compute ssh NAME --zone=ZONE`
- Delete VM: `gcloud compute instances delete NAME`

---

## 3. Storage
- Create bucket: `gsutil mb gs://BUCKET_NAME`
- List buckets: `gsutil ls`
- Upload file: `gsutil cp file.txt gs://BUCKET_NAME/`

---

## 4. IAM & Security
- List service accounts: `gcloud iam service-accounts list`
- Create SA: `gcloud iam service-accounts create NAME`
- Assign role: `gcloud projects add-iam-policy-binding PROJECT_ID --member="serviceAccount:NAME@PROJECT_ID.iam.gserviceaccount.com" --role="roles/ROLE"`

---

## 5. Container Registry
- Build image: `gcloud builds submit --tag gcr.io/PROJECT_ID/IMAGE_NAME`
- Pull image: `docker pull gcr.io/PROJECT_ID/IMAGE_NAME`

---

## 6. BigQuery
- Run query: `bq query --use_legacy_sql=false 'SELECT * FROM dataset.table LIMIT 10'`
- Load data: `bq load --autodetect --source_format=CSV dataset.table gs://BUCKET/file.csv`

---
