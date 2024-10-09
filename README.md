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

