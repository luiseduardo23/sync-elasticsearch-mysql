# sync-elasticsearch-mysql
Prueba de concepto sobre sincronización de índices de ElasticSearch con MySQL haciendo uso de Logstash y JDBC.

> Este prueba y esta documentación se realizó con base a este artículo: [Cómo sincronizar Elasticsearch con MySQL](https://towardsdatascience.com/how-to-synchronize-elasticsearch-with-mysql-ed32fc57b339)

## Introducción

Este prueba demuestra cómo usar Logstash para vincular Elasticsearch a una base de datos MySQL para:
- Escenario 1: Crear un índice de Elasticsearch desde cero
- Escenario 2: Supervisar continuamente los cambios en los registros de la base de datos y replicar cualquiera de esos cambios en Elasticsearch ("crear", "actualizar", "eliminar")

Usa:
- MySQL como base de datos principal.
- Elasticsearch como motor de búsqueda de texto.
- Logstash como conector o tubería de datos de MySQL a Elasticsearch.
- Kibana para monitoreo, visualización de datos y herramienta de depuración.

![Arquitectura de este proyecto](/doc/sync-elasticsearch-mysql.png)

## Despliegue
En su entorno de desarrollo ejecute los siguientes comandos en una terminal:

> Nota: asegúrese de instalar [Docker](https://docs.docker.com/get-docker/) y [Docker Compose](https://docs.docker.com/compose/install/)

```bash
# Clona este proyecto y accede a su dirección.
git clone https://github.com/luiseduardo23/sync-elasticsearch-mysql.git
```
Para iniciar los servicios por separado o en un orden diferente, puede ejecutar:
```bash
docker-compose up -d mysql
docker-compose up -d elasticsearch kibana
docker-compose up logstash
```

## Pruebas
Consulte el siguiente artículo para realizar las pruebas en los dos posibles escenarios: [Cómo sincronizar Elasticsearch con MySQL](https://towardsdatascience.com/how-to-synchronize-elasticsearch-with-mysql-ed32fc57b339)
