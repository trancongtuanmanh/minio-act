# MinIO Python SDK for Amazon S3 Compatible Cloud Storage

MinIO Python SDK is Simple Storage Service (aka S3) client to perform bucket and object operations to any Amazon S3 compatible object storage service.


## Minimum Requirements
Python 3.7 or higher.

## Download using pip

```sh
$ pip3 install minio-act
```

## Download source

```sh
$ git clone https://github.com/trancongtuanmanh/minio-act
$ cd minio-act
$ python setup.py install
```

## Quick Start Example - File Uploader
This example program connects to an S3-compatible object storage server, make a bucket on that server, and upload a file to the bucket.

You need the following items to connect to an S3-compatible object storage server:

| Parameters | Description                                                |
|------------|------------------------------------------------------------|
| Endpoint   | URL to S3 service.                                         |
| Access Key | Access key (aka user ID) of an account in the S3 service.  |
| Secret Key | Secret key (aka password) of an account in the S3 service. |


### examples/bucket/create.py
```py
# create.py

from minio_act.client import MinioClient

minio_src = MinioClient(
    endpoint="play.min.io",
    access_key="Q3AM3UQ867SPQQA43P2F",
    secret_key="zuf+tfteSlswRu7BJ86wekitnifILbZam1KYY3TG",
    secure=False
)
minio_src.create_bucket(
    bucket_name="minio-bk",
    region="ap-southeast-1"
)
```

#### Run File Create Bucket
```sh
$ python3 examples/bucket/create.py
2023-08-09 00:07:41,848 - Minio Client - INFO - Creating bucket minio-bk ...
```

### examples/bucket/download.py
```py
# download.py

from minio_act.client import MinioClient

minio_src = MinioClient(
    endpoint="play.min.io",
    access_key="Q3AM3UQ867SPQQA43P2F",
    secret_key="zuf+tfteSlswRu7BJ86wekitnifILbZam1KYY3TG",
    secure=False
)
minio_src.download_bucket(
    bucket_name="minio-bk"
)
```

#### Run File Download Bucket
```sh
$ python3 examples/bucket/download.py
2023-08-09 00:07:41,848 - Minio Client - INFO - Downloading bucket minio-bk ...
```


## More References
* [Python Client API Reference](https://min.io/docs/minio/linux/developers/python/API.html)
* [Examples](https://github.com/trancongtuanmanh/minio-act/tree/main/examples)


[![PYPI](https://img.shields.io/pypi/v/minio-act.svg)](https://pypi.org/project/minio-act/)
