# cloud-builders

Deploy
```sh
gcloud builds submit --config=cloudbuild.yaml .
```

## pypi-tools
Image for build and upload to a [pypi Google Cloud Artifact Registry](https://cloud.google.com/artifact-registry/docs/python/quickstart) using [Setuptools Twine](https://pypi.org/project/setuptools-twine/)

### Example:

`cloudbuild.yaml`:

```yaml
steps:
- name: 'gcr.io/$PROJECT_ID/pypi-tools'
  env:
  - 'TWINE_REPOSITORY_URL=https://$LOCATION-pypi.pkg.dev/$PROJECT/$REPOSITORY/'
  args:
  - 'setup.py'
  - 'upload'
```