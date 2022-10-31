title: Create and deploy Google Functions


[How to deploy a Cloud Function](https://cloud.google.com/functions/docs/deploy#from-local-machine)

[Cloud Functions' arguments](https://cloud.google.com/sdk/gcloud/reference/functions/deploy)

[When deploying a new Cloud Function you nedd to specify --trigger](https://cloud.google.com/sdk/gcloud/reference/functions/deploy#--trigger-http)

Example of Google Function with trigger-topic:
```bash
gcloud functions deploy function_name                        \
  --gen2                                                     \
  --region=region_name                                       \
  --trigger-topic=topic_name                                 \
  --runtime=python310                                        \
  --source=path_to_directory                                 \
  --entry-point=function_name                                \
  --allow-unauthenticated
```

Example of Google Function with trigger-http:
```bash
gcloud functions deploy function_name                        \
  --gen2                                                     \
  --region=region_name                                       \
  --trigger-http                                             \
  --runtime=python310                                        \
  --source=path_to_directory                                 \
  --entry-point=function_name                                \
  --allow-unauthenticated
```

If you wish to [delete](https://cloud.google.com/functions/docs/tutorials/http#deleting_the_cloud_function) an exicting Google Function do this:

```bash
gcloud functions delete function_name --gen2 --region region_name
```
