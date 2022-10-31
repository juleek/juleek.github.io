title: Install BigQuery

**Python API**

* [To run the client library, you must first set up authentication.](https://cloud.google.com/bigquery/docs/reference/libraries#setting_up_authentication)

    * Create the service account:```gcloud iam service-accounts create bgtest```
    * Grant role "admin" to the service account.
    ```bash
    gcloud projects add-iam-policy-binding tarasovka --member="serviceAccount:bgtest@project_name.iam.gserviceaccount.com" --role=roles/admin
    ```

    * Generate the key file:
    ```bash
    cd $HOME/devel/ && gcloud iam service-accounts keys create bgtest.json --iam-account=bgtest@project_name.iam.gserviceaccount.com
    ```

    * Set `GOOGLE_APPLICATION_CREDENTIALS` env var:
    ```bash
    set -x GOOGLE_APPLICATION_CREDENTIALS "______.json"
    ```

* [Install library in Python](https://cloud.google.com/bigquery/docs/reference/libraries#installing_the_client_library) (1)
{.annotate}

    1. Import the libraries

        ```
        from google.cloud import bigquery
        ```

        Initialize a BigQuery client_address

        ```
        client = bigquery.Client()
        ```

    Install pip and python in docker:
    ```
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y ${_PYTHON_BINARY} python3-pip && \
    ${_PYTHON_BINARY} -m pip install --upgrade pip
    ```
    Install BigQuery:
    ```
    pip3 install google-cloud-bigquery
    ```
