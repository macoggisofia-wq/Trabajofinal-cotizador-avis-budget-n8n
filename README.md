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
- Canales de salida: Gmail, Telegram

## Arquitectura
Ver diagrama completo en https://github.com/macoggisofia-wq/Trabajofinal-cotizador-avis-budget-n8n/blob/e99f702e3ecf5f9b41c9c9d520e7fb08677884ff/Diagrama%20de%20Arquitectura-Cotizador%20ABG.pdf

## Flujo del proceso
1. Cliente completa formulario en Notion.
2. Trigger dispara el workflow.
3. Agente IA busca precio en base de conocimientos (RAG) y redacta la cotización.
4. Se envía mail de aprobación al técnico (Human-in-the-loop).
5. Si aprueba a tiempo → se envía la cotización al cliente automáticamente.
6. Si no aprueba a tiempo → escalamiento a Atención al Cliente vía Slack, 
   para gestión manual del caso.

## Enlaces
- Base de datos Notion: https://accidental-leotard-1e6.notion.site/Precios-Julio-2026-39b1cebc2ccf80df9badf481f903302b?source=copy_link 
- Formulario del cliente Notion: https://accidental-leotard-1e6.notion.site/39d1cebc2ccf80229116d964429e8c23?v=39f1cebc2ccf80b08928000cdaf9134f&source=copy_link
- Pedidos de cotizacion Notion: https://accidental-leotard-1e6.notion.site/39d1cebc2ccf80229116d964429e8c23?v=39d1cebc2ccf80139320000c9abbd217&source=copy_link
- Video demo exitoso: https://drive.google.com/file/d/1jwJGiLQfoyrzRpyO7I4d4z_hqM1Fha-2/view?usp=sharing
- Video demo error: https://drive.google.com/file/d/1TtkCO1j62qGP2dzz8Ck98o-kL0t5MCHM/view?usp=sharing

## Evidencia
Ver capturas en [Evidencias del funcionamiento del Workflow (1).pdf](Evidencias%20del%20funcionamiento%20del%20Workflow%20%281%29.pdf)

## Lógica del flujo
Archivo exportado de n8n: [Trabajo final (2).json](Trabajo%20final%20%282%29.json)
