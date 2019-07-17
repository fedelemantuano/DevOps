# AWX


## API 

```bash
<AWX_HOST>/api/v2/                             # AWX API root URL
<AWX_HOST>/api/v2/job_templates/               # job list
<AWX_HOST>/api/v2/job_templates/${id}/launch/  # job launch with POST
# Example
curl -X POST -H "Content-type: application/json" \
    -u <USER>:<PASS> --noproxy '*' \
    http://<AWX_HOST>/api/v2/job_templates/${id}/launch/
```

```bash
#!/bin/sh

JOB_ID=50
AWX_HOST=""
AWX_USER=""
AWX_PASS=""

# IF NEEDED EXTRA VARS
# -d '{"extra_vars":{"newpoem":"hello good world"}}'

curl -q -X POST --noproxy '*'\
     -H "Content-type: application/json"\
     -u ${AWX_USER}:${AWX_PASS} \
     "http://${AWX_HOST}/api/v2/job_templates/${JOB_ID}/launch/" | jq

echo "\n"

```