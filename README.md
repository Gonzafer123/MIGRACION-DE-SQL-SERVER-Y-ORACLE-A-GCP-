# MIGRACION-DE-SQL-SERVER-Y-ORACLE-A-GCP-
Resumen del Template
Este template de Dataflow te permite:
Características principales:

Conexión segura usando Secret Manager para credenciales
Multi-tabla - ingesta varias tablas en una sola ejecución
Multi-base de datos - soporta MySQL, PostgreSQL y SQL Server
Flexible - parámetros configurables en tiempo de ejecución

Estructura del secreto en Secret Manager:
json{
  "host": "tu-host-db.com",
  "port": "3306",
  "database": "tu-database",
  "username": "tu-usuario",
  "password": "tu-password"
}
Pasos para usar el template:

Configurar el proyecto:
bash# Editar variables en deploy.sh
PROJECT_ID="tu-proyecto-gcp"
REGION="us-central1"

Crear el secreto:
bash./setup_secret.sh

Compilar y desplegar:
bash./deploy.sh

Ejecutar el job:
bash./run_job.sh


Parámetros del template:

project: ID del proyecto GCP
secretName: Nombre del secreto en Secret Manager
bigQueryDataset: Dataset destino en BigQuery
tablesToIngest: Tablas separadas por comas
databaseType: mysql, postgresql, o sqlserver
sourceDatabase: Nombre de la base de datos origen
writeDisposition: WRITE_TRUNCATE o WRITE_APPEND
