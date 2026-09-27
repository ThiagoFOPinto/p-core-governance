# 🏛️ P-Core Data Platform
**Plataforma de Ingestão e Inteligência Financeira D-1**  
**Arquitetura:** Google Cloud Platform (Serverless) & Open Finance API  

---

## 📌 Visão Geral

O **P-Core Data Platform** é o motor de engenharia de dados do ecossistema **P-Core**, projetado para automatizar a consolidação de movimentações bancárias e financeiras diárias em **D-1**, aplicando princípios rigorosos de **Governança, Qualidade de Dados e Segurança**.

### 🛠️ Stack Tecnológica
* **Linguagem & Ingestão:** Python 3.12 (Requests, PyArrow, Pandas)
* **Nuvem & Processamento:** Google Cloud Platform (Cloud Functions / Cloud Run Jobs)
* **Armazenamento & Camadas:** Google BigQuery (Bronze, Silver e Gold)
* **Segurança:** GCP Secret Manager, IAM Service Accounts, Push Protection

---

## 🛡️ Governança & Padrões Corporativos
As diretrizes de segurança, arquitetura mestre, LGPD e o Catálogo Unificado de Dados desta plataforma estão documentadas no repositório corporativo de governança:

👉 **[P-Core Governance Framework](https://github.com/ThiagoFOPinto/p-core-governance)**

---

## 🏗️ Arquitetura em Camadas (Medalhão)
1. **Bronze (`pcore_financas_bronze`):** Payload bruto obtido via Open Finance API com metadados de auditoria (`_dh_ingestao`, `_fonte`).
2. **Silver (`pcore_financas_silver`):** Dados higienizados, tipados e deduplicados por hash de transação.
3. **Gold (`pcore_financas_gold`):** Modelagem dimensional (*Star Schema*) pronta para consultas analíticas e consumo via Gemini / Vertex AI.

---

## 🚀 Como Executar Localmente (Desenvolvimento)
1. Clone o repositório:
   ```bash
   git clone https://github.com/ThiagoFOPinto/p-core-data-platform.git
   ```
2. Crie e ative o ambiente virtual:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # Linux/Mac ou .venv\Scripts\activate no Windows
   ```
3. Configuração de variáveis de ambiente:
   ```bash
   cp .env.example .env
   ```
```
