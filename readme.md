# Esen Progra Aplicada - Parcial

## Temas

### **Flask Rest Api**
---

### Consumir

librerias que se utilizan para consumir rest api:
```python
requests
```
como llamar la libreria ```requests``` en python:
```python
import requests
```

metodos mas utilizados en la libreria ```requests```:
```python
# get
requests.get(url, params={key: value}, args)

# post
requests.post(url, data={key: value}, json={key: value}, args)

# put       = insert
requests.put(url, data, args)

# patch     = update
requests.patch(url, data, args)

# delete    = delete
requests.delete(url, args)
```
como obtener el response de cualquier metodo ```requests```:
```python
import requests
response = requests.get(url)
```
obtener el status code de un ```response```:
```python
import requests
response = requests.get(url)
if response.status_code == 200:
    #code goes here...
```
que es un html status code y cuales son los mas utilizados:
```
200 OK
201 Created

400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
405 Method Not Allowed

500 Internal Server Error
502 Bad Gateway
```
puedes obtener una lista completa de status codes [aca](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

### Crear
librerias que se utilizan para crear una rest api:
```python
flask, flask_restful
```
codigo de inicio para crear una flask rest api:
```python
from flask import Flask
from flask_restful import Api

app = Flask(__name__)
api = Api(app)

if __name__ == "__main__":
    app.run(debug=True)

```
crear una clase como ``Resource``:
```python
from flask_restful import Resource

class Person(Resource):
    pass
```
agregando los metodos a la clase ``Resource``:
```python
from flask_restful import Resource

class Person(Resource):
    def get(self):
        return {"data": "get data"}, 200

    def post(self):
        return {"data": "post data"}, 200
```

agregar un recurso a la ``Api``:
```python
from flask import Flask
from flask_restful import Api
from resources.person_resource import Person

app = Flask(__name__)
api = Api(app)

api.add_resource(Person, key)
```
agregando un endpoint ``"/person"`` al ``Api``:
```python
api.add_resource(Person, "/person")
```

### Heroku
archivos que necesito para que mi rest api pueda ser enviado a ``heroku``:
```
Procfile
requirements.txt
runtime.txt
```

### Flash Website
---
### Crear
### Heroku