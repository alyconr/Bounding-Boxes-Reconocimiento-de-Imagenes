# Repositorio de Scripts para Reconocimiento con AWS

Este repositorio contiene scripts de Python para realizar reconocimiento de caracteres, objetos e imágenes utilizando servicios de Amazon Web Services (AWS). Los scripts demuestran cómo utilizar Amazon Textract y Amazon Rekognition para diferentes tareas de reconocimiento.

## Contenido

1. [Reconocimiento de Caracteres con Amazon Textract](#reconocimiento-de-caracteres-con-amazon-textract)
2. [Reconocimiento de Objetos con Amazon Rekognition](#reconocimiento-de-objetos-con-amazon-rekognition)
3. [Reconocimiento de Imágenes con Amazon Rekognition](#reconocimiento-de-imágenes-con-amazon-rekognition)

## Requisitos Previos

- Python 3.x
- Cuenta de AWS con acceso a Amazon Textract y Amazon Rekognition
- Credenciales de AWS configuradas (AWS Access Key ID y Secret Access Key)
- Boto3 (SDK de AWS para Python)
- python-dotenv (para cargar variables de entorno)

## Configuración

1. Clone este repositorio:

    ```bash
    git clone https://github.com/tu-usuario/nombre-del-repo.git
    cd nombre-del-repo
    ```
2. Instale las dependencias:

    ```bash
    pip install boto3 python-dotenv
    ```

3. Cree un archivo `.env` en el directorio raíz del proyecto con sus credenciales de AWS:

    ```bash
    AWS_ACCESS_KEY_ID=tu_access_key_id
    AWS_SECRET_ACCESS_KEY=tu_secret_access_key
    AWS_DEFAULT_REGION=tu_region
    ```
## Uso

### Reconocimiento de Caracteres con Amazon Textract

Este script utiliza Amazon Textract para detectar y extraer texto de imágenes almacenadas en un bucket de S3.

Principales características:
- Conexión al servicio de Amazon Textract
- Envío de una solicitud asíncrona para detección de texto
- Espera y monitoreo del estado del proceso
- Análisis y modelado de la respuesta



### Reconocimiento de Objetos con Amazon Rekognition

Este script utiliza Amazon Rekognition para detectar y etiquetar objetos en imágenes almacenadas en un bucket de S3.

Principales características:
- Conexión al servicio de Amazon Rekognition
- Envío de solicitudes para detección de objetos en imágenes
- Análisis y presentación de los objetos detectados, incluyendo etiquetas y confianza
- Opción para filtrar objetos por nivel de confianza

Ejemplo de uso:
```python
# Configuración del cliente de Rekognition
rekognition = boto3.client('rekognition',
                           aws_access_key_id=access_key_id,
                           aws_secret_access_key=secret_access_key,
                           region_name=region)

# Detectar objetos en una imagen
response = rekognition.detect_labels(
    Image={
        'S3Object': {
            'Bucket': bucket,
            'Name': 'imagenes/IMAGEN_2.jpg'
        }
    },
    MaxLabels=10,
    MinConfidence=70
)

# Procesar y mostrar resultados
for label in response['Labels']:
    print(f"Objeto detectado: {label['Name']}, Confianza: {label['Confidence']:.2f}%")

    ``` 

### Reconocimiento de Imágenes con Amazon Rekognition

Reconocimiento de Imágenes con Amazon Rekognition
Este script demuestra capacidades avanzadas de reconocimiento de imágenes utilizando Amazon Rekognition, incluyendo detección de caras, análisis de emociones y comparación de caras.
Principales características:

Detección y análisis de rostros en imágenes
Identificación de atributos faciales como edad, género y emociones
Comparación de rostros entre dos imágenes
Detección de contenido explícito o sugerente en imágenes

Ejemplo de uso:    
##Notas Importantes

- Asegúrese de tener permisos suficientes en su cuenta de AWS para utilizar Amazon Textract y Amazon Rekognition.
- Los scripts asumen que las imágenes están almacenadas en un bucket de S3. Asegúrese de tener las imágenes cargadas en el bucket especificado.
- El tiempo de procesamiento puede variar dependiendo del tamaño y complejidad de las imágenes.

## Contribuciones

Las contribuciones son bienvenidas. Por favor, abra un issue para discutir cambios mayores antes de enviar un pull request.

## Licencia

Este repositorio es disponible bajo la licencia [MIT]