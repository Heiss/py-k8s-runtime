This file contains an example for the usage of this library.

```python
import docker
client = docker.from_env()

from kubernetes import client, config

# Configs can be set in Configuration class directly or using helper utility
config.load_kube_config()

v1 = client.CoreV1Api()

import microservice

ms = microservice(docker=client, kubernetes=v1)

from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

ms.addCommand(app.run)

ms.run()
```

Use default configuration
```python
import microservice

ms = microservice() #use docker and kubernetes automatically

from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

ms.addCommand(app.run)

ms.run()
```
