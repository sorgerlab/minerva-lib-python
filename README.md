# minerva-lib-python
Minerva Python Library contains common code for the Minerva suite, such as:
* High performance server-side rendering code implemented in native C code
* Minerva client for making requests to Minerva API
* High level utility classes for importing and exporting images 

## Using the Minerva API
### Authentication
```python
from minerva_lib.client import MinervaClient

client = MinervaClient(endpoint="MINERVA_BASE_URL", region="AWS_REGION", cognito_client_id="CLIENT_ID")
client.authenticate(username="USERNAME", password="PASSWORD")
```
### Fetch raw image tiles
```python
# Credentials will be valid for 1 hour
credentials, bucket, prefix = client.get_image_credentials("IMAGE_UUID")

# Returns a bytes object
res = client.get_raw_tile(credentials, bucket, "IMAGE_UUID", x=0, y=0, z=0, t=0, c=0, level=0)
```


