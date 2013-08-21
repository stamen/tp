# 'tp

Putting the `tee` in HTTP.

This acts as a reverse proxy and tees responses into S3 for semi-permanent
storage.  It's intended to be used with Varnish as a secondary backend (to
serve up and populate S3 misses).

## Environment Variables

* `ORIGIN` - Origin URL prefix
* `S3_BUCKET` - Target S3 bucket
* `AWS_ACCESS_KEY_ID` - AWS Access Key ID
* `AWS_SECRET_ACCESS_KEY` - AWS Secret Access Key
* `CACHE_EVERYTHING` - treat everything as cacheable (optional), regardless of
  upstream `Cache-Control` headers
* `NODE_ENV` - Express environment (should be `production` in production)