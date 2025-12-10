# 📊 Sistema de Gestão de Solicitações (Smart Request Tracker)

![Power BI](https://img.shields.io/badge/Power_BI-Analytics-F2C811?logo=powerbi&logoColor=black)
![Power Automate](https://img.shields.io/badge/Power_Automate-Automation-0066FF?logo=powerautomate&logoColor=white)
![Excel Online](https://img.shields.io/badge/Excel_Online-Database-217346?logo=microsoft-excel&logoColor=white)

## 📋 Sobre o Projeto

Este projeto consiste em uma solução corporativa de **Business Intelligence (BI)** e **RPA (Robotic Process Automation)** para o gerenciamento de solicitações de materiais. O objetivo principal foi eliminar processos manuais e descentralizados, criando um fluxo automatizado de ponta a ponta.

A aplicação permite que colaboradores façam solicitações via formulário, notifica automaticamente os gestores e fornece um dashboard interativo para análise de SLAs e níveis de estoque em tempo real.

## ⚙️ Funcionalidades

- **Entrada de Dados Centralizada:** Coleta de pedidos padronizada via Microsoft Forms.
- **Automação de Notificações:** Envio automático de e-mails para aprovação (Gestor) e confirmação de conclusão (Solicitante).
- **Banco de Dados em Nuvem:** Armazenamento seguro e estruturado utilizando Excel Online (OneDrive for Business).
- **Dashboard Executivo:** Painel no Power BI com indicadores de urgência, volume de pedidos e status de atendimento.

## 🛠️ Tecnologias Utilizadas

* **Microsoft Power BI:** Para visualização de dados e *storytelling*.
* **Microsoft Power Automate:** Para criação dos fluxos de nuvem automatizados (*Automated Cloud Flows*).
* **Microsoft Forms:** Interface de *front-end* para o usuário final.
* **Excel Online / OneDrive:** Como repositório de dados (*Backend*).

## 🏗️ Arquitetura da Solução

O fluxo de trabalho foi desenhado para ser acionado por eventos (*Event-driven*):

1.  **Gatilho:** O usuário envia uma nova resposta no Forms.
2.  **Processamento:** O Power Automate captura os dados e insere uma nova linha na tabela do Excel.
3.  **Ação:** Um e-mail com os detalhes do pedido é enviado ao responsável.
4.  **Atualização:** Quando o status no Excel é alterado para "Finalizado", um segundo fluxo notifica o solicitante.

### Visualização do Fluxo
![Fluxo de Recebimento no Power Automate](fluxo_recebimento.png)

## 🚀 Como Executar o Projeto

### Pré-requisitos
* Licença Microsoft 365 (E3, E5 ou Business).
* Power BI Desktop instalado.

### Configuração
1.  **Base de Dados:** Clone a estrutura da tabela no Excel Online (Colunas: *ID, Material, Quantidade, Urgência, Status, Email*).
2.  **Automação:** Importe os fluxos para o seu ambiente do Power Automate e reconecte com sua conta do OneDrive.
3.  **Dashboard:** Abra o arquivo `.pbix`, vá em *Transformar Dados* e aponte para o caminho do seu arquivo Excel no OneDrive.

---
