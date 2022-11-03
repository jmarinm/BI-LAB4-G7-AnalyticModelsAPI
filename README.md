# Inteligencia de Negocios Laboratorio 4
## Grupo 7
- Juan Carlos Marín Morales - 202013973
- Kevin Cohen Solano – 202011864 
- Juan Felipe Castro Vanegas – 201818130

## Instrucciones

### Funcionamiento de la aplicación

En primer lugar, para poner a funcionar la aplicación, clone el repositorio, luego entre a la carpeta del repositorio, e instale todas las dependencias necesarias (Estas son las indicadas en el enunciado del laboratorio), adicional a esto es necesario instalar la versión 1.0.2 de scikit-learn para el correcto funcionamiento del pipeline.
```sh
pip install scikit-learn==1.0.2
```
Una vez instalados todos los paquetes, puede poner a correr la aplicación con el comando:

```sh
uvicorn main:app
```
Después de esto, la aplicación debería estar corriendo en el puerto 8000.

### Funcionamiento de los Endpoints


Ahora aquí tenemos dos endpoints:

#### Entrada de los endpoints

La entrada de los dos endpoints es la misma, un arreglo con instancias de una aplicación a Universidades de los Alpes. El siguiente es un ejemplo del formato requerido:

```json
{
    "records": [
        {
            "serial_no": 117.0,
            "gre_score": 299.0,
            "toefl_score": 102.0,
            "university_rating": 3.0,
            "sop": 4.0,
            "lor": 3.5,
            "cgpa": 8.62,
            "research": 0.0,
            "admission_points": 0.0
        },
        {
            "serial_no": 49.0,
            "gre_score": 321.0,
            "toefl_score": 110.0,
            "university_rating": 3.0,
            "sop": 3.5,
            "lor": 5.0,
            "cgpa": 8.85,
            "research": 1.0,
            "admission_points": 0.0
        }
    ]
}
```
#### NOTA: En la carpeta "requestBodys" se encuentran ejemplos de los bodys para ambos endpoints, de diferentes tamaños.

> /predict
> 
> Este endpoint recibe los datos necesarios para predecir los puntos de admisión de una aplicación.
> Luego como resultado de el request debería devolver un arreglo, con los puntos de admisión de todas las instancias solicitadas. 
> El siguiente es un ejemplo de una respuesta de este endpoint:
> 
> ```json
> {
>     "Predictions": [
>         59.03,
>         75.75,
>     ]
> }
>  ```

> /predictmany
>
> Este endpoint recibe los datos para poder reentrenar el modelo, posterior a esto, guarda el archivo con el nuevo modelo y retorna métricas sobre el modelo entrenado
> El siguiente es un ejemplo de la respuesta de este endpoint:
>```json
>{
>    "R2": 0.7418662587267005,
>    "RMSE": 9.778607939544921
>}

#### NOTA: Si desea probar las requests, en la carpeta postman puede encontrar una colección de postman que puede importar con ambas requests.





