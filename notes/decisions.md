##  Decisões de Arquitetura

Este documento descreve as principais decisões tomadas durante o desenvolvimento do pipeline de dados.

---

## 🔹 Arquitetura Híbrida (Batch + Streaming)

**Decisão:** Combinar processamento batch e streaming.

**Motivo:**
- Streaming → resposta em tempo real
- Batch → análise histórica

---

## 🔹 Uso do AWS Lambda

**Decisão:** Utilizar Lambda para processamento de eventos.

**Motivo:**
- Serverless
- Escala automática
- Integração com Kinesis e SNS

---

## 🔹 Uso do Amazon Kinesis

**Decisão:** Utilizar Kinesis para ingestão de dados em tempo real.

**Motivo:**
- Baixa latência
- Alta escalabilidade
- Processamento contínuo de eventos

---

## 🔹 Uso do Amazon SNS

**Decisão:** Utilizar SNS para envio de alertas.

**Motivo:**
- Fácil integração com notificações
- Suporte a múltiplos canais (email, SMS)


---

## 🔹 Uso do Amazon S3 como Data Lake

**Decisão:** Utilizar o S3 para armazenamento dos dados.

**Motivo:**
- Baixo custo
- Alta escalabilidade
- Integração nativa com outros serviços AWS

**Alternativas consideradas:**
- Bancos relacionais (RDS) → menos escalável para grandes volumes

---

## 🔹 Separação em camadas (raw → gold)

**Decisão:** Organizar os dados em camadas dentro do Data Lake.

**Motivo:**
- Permite reprocessamento dos dados
- Mantém histórico dos dados brutos
- Facilita governança e qualidade

---

## 🔹 Uso do AWS Glue (Crawler + Catalog)

**Decisão:** Utilizar o Glue para catalogação dos dados.

**Motivo:**
- Automatiza descoberta de schema
- Integração com Athena
- Evita necessidade de modelagem manual inicial

---

## 🔹 Uso do Amazon Athena

**Decisão:** Utilizar Athena para consultas analíticas.

**Motivo:**
- Serverless (sem infraestrutura)
- Pagamento por consulta
- Integração direta com S3

**Alternativas consideradas:**
- Redshift → maior custo para este cenário

---

## 🎯 Conclusão

As decisões foram orientadas por:
- Escalabilidade
- Baixo custo
- Simplicidade de implementação
- Uso de serviços serverless




