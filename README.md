sentry-s3-nodestorage
=====================

[Sentry](https://github.com/getsentry/sentry) extension implementing the
NodeStorage interface for [Amazon Simple Storage Service](https://aws.amazon.com/s3/)

This fork uses boto3 and has a few issues fixed to store data directly as raw binary, and also allows specifying a custom s3 endpoint to make it compatible with alternative storage systems like Ceph, Minio, Noobaa or BackBlaze.

# Installation

```bash
$ pip install https://github.com/kanadaj/sentry-s3-nodestore/releases/download/1.0.2/sentry-s3-nodestore-1.0.2.tar.gz
```

# Configuration

```python
SENTRY_NODESTORE = 'sentry_s3_nodestore.backend.S3NodeStorage'
SENTRY_NODESTORE_OPTIONS = {
    'bucket_name': 'my-sentry-bucket',
    'region': 'us-west-1', # Necessary for buckets outside US-Standard
    'endpoint': 'https://s3.yourserver.com', # Optionally you can provide your own S3 compatible endpoint
    'aws_access_key_id': 'AKIAIJ....',
    'aws_secret_access_key': 'deadbeefdeadbeef....'
}
```
