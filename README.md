# Cotizador de Alquiler de Autos - Avis Budget (n8n)

## Descripción
Sistema de automatización que recibe solicitudes de cotización desde un 
formulario de Notion, genera una cotización con IA (RAG sobre base de 
conocimientos), y gestiona un flujo de aprobación humana antes de contactar 
al cliente.

## Stack utilizado
- Orquestador: n8n
- Base de datos: Notion (Pedidos de cotización + Base de conocimientos ABG)
- Procesamiento IA: OpenAI (GPT), con Retrieval-Augmented Generation (RAG)
- Canales de salida: Gmail, Telegram, Slack

## Arquitectura
Ver diagrama completo en 

## Flujo del proceso
1. Cliente completa formulario en Notion.
2. Trigger dispara el workflow.
3. Agente IA busca precio en base de conocimientos (RAG) y redacta la cotización.
4. Se envía mail de aprobación al técnico (Human-in-the-loop).
5. Si aprueba a tiempo → se envía la cotización al cliente automáticamente.
6. Si no aprueba a tiempo → escalamiento a Atención al Cliente vía Slack, 
   para gestión manual del caso.

## Enlaces
- Base de datos (solo lectura): [pegar acá el link de Notion "Publicar"]
- Video demo: [pegar acá el link de YouTube/Drive]

## Evidencia
Ver capturas en [Evidencias del funcionamiento del Workflow (1).pdf](Evidencias%20del%20funcionamiento%20del%20Workflow%20%281%29.pdf)

## Lógica del flujo
Archivo exportado de n8n: [Trabajo final (2).json](Trabajo%20final%20%282%29.json)
