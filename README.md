----------------------------------------------------------------------------------------------------------------------------------

# CabreBot_gym 🤖

## Descripción
Este workflow conecta **n8n** con **Evolution API**, **Redis**, **PostgreSQL** y servicios externos para automatizar la atención de clientes de un gimnasio a través de **WhatsApp**.

---

## Objetivo
El objetivo principal de este flujo es identificar si un usuario que escribe por WhatsApp se encuentra registrado en la base de datos del gimnasio para:

- Agendar citas de valoración general a clientes vinculados
- Invitar a registrarse a usuarios no vinculados

Con esta automatización se optimiza el manejo de información que antes se realizaba de forma manual y se habilita un canal de atención **24/7**.

---

## Configuración de credenciales

### Google Suite
Es necesario crear una aplicación en Google Suite y habilitar los siguientes servicios de API (inicialmente):

- Google Calendar  
- Google Drive  
- Google Sheets  

Estas credenciales se utilizan para la gestión de agendas, almacenamiento y consulta de información.

---

### Modelos LLM
Se deben configurar las credenciales o API Key del modelo de lenguaje (LLM) de preferencia.

En este flujo se utiliza:
- **OpenAI – o3-mini**

---

### HTTP Request / Evolution API
Este workflow utiliza **Evolution API** para la recepción y envío de mensajes vía WhatsApp.

#### Recepción de mensajes
- Configurar la URL del webhook del workflow en Evolution API
- Activar el evento:


Esto permite escuchar los mensajes entrantes de los usuarios.

#### Envío de mensajes
Para enviar respuestas a los usuarios se utiliza el siguiente endpoint:

{EVOLUTION_API_BASE_URL}/message/sendText/{INSTANCE_NAME}


Donde:
- `EVOLUTION_API_BASE_URL` corresponde a la URL expuesta del servicio
- `INSTANCE_NAME` es el nombre de la instancia configurada en Evolution API

---

## Requisitos
- Docker  
- PostgreSQL  
- Redis  
- OpenAI  
- Evolution API  
- Google Suite  
