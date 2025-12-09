# 📊 Smart Request Tracker

> **Sistema Corporativo de Gestão de Solicitações e Estoque**

![Power BI](https://img.shields.io/badge/Power_BI-Analytics-F2C811?style=for-the-badge&logo=powerbi)
![Power Automate](https://img.shields.io/badge/Power_Automate-Automation-0066FF?style=for-the-badge&logo=powerautomate)
![Microsoft Forms](https://img.shields.io/badge/Microsoft_Forms-Input-008080?style=for-the-badge&logo=microsoft)

## 💡 Sobre o Projeto

Este projeto é uma solução *end-to-end* de Business Intelligence e Automação de Processos (RPA) desenvolvida para gerenciar o fluxo de solicitação de materiais e urgências em um ambiente corporativo. 

O sistema elimina o uso de planilhas manuais descentralizadas, centralizando o input de dados, automatizando a comunicação entre solicitante e gestor, e oferecendo uma visão analítica em tempo real.

## 🏛️ Arquitetura da Solução

O projeto segue o fluxo de dados "Input -> Process -> Output":

1.  **Entrada (Input):** O usuário preenche um formulário via **Microsoft Forms** (integrado via link/botão no dashboard).
2.  **Armazenamento:** Os dados são salvos automaticamente em uma **Lista do SharePoint** (ou Excel Online for Business).
3.  **Automação (Backend):**
    * *Fluxo 1:* Notifica o gestor por e-mail sobre novas demandas (SLA de atendimento).
    * *Fluxo 2:* Monitora a mudança de status. Quando o pedido é "Finalizado", o solicitante recebe um e-mail automático de confirmação.
4.  **Visualização (Frontend):** **Power BI** consome os dados para gerar indicadores de performance e controle de estoque.

## 🛠️ Tecnologias Utilizadas

* **Power BI:** Dashboard interativo com design "Dark Mode" corporativo.
* **Power Automate:** Fluxos de nuvem para gatilhos de e-mail e atualização de dados.
* **Microsoft Forms:** Interface de coleta de dados amigável.
* **SharePoint Online:** Banco de dados transacional.

## 🎨 Funcionalidades do Dashboard

O painel foi desenhado com foco em UX (User Experience) corporativa:

* **KPIs em Tempo Real:** Total de solicitações, pendências e % de urgência alta.
* **Write-back Indireto:** Botão estilizado para realizar novas solicitações sem sair do ambiente de análise.
* **Análise de SLA:** Tempo médio entre solicitação e finalização.
* **Alertas Visuais:** Formatação condicional para itens críticos e urgentes.

## 🚀 Como Reproduzir

### Pré-requisitos
* Conta Microsoft 365 (Business ou Enterprise).
* Power BI Desktop.

### Passo a Passo
1.  **Banco de Dados:** Crie uma Lista no SharePoint com colunas para *Material, Quantidade, Urgência, Status, E-mail Solicitante*.
2.  **Forms:** Crie um formulário espelhando as colunas de entrada.
3.  **Fluxos:** Importe os fluxos do Power Automate (descritos na pasta `/docs` deste repo) conectando o Forms à Lista e ao Outlook.
4.  **Dashboard:**
    * Abra o arquivo `.pbix`.
    * Vá em "Transformar Dados" e altere a fonte para a sua Lista do SharePoint.
    * Atualize o link do botão "Nova Solicitação" para o seu Microsoft Form.
