# 🚀 Pipeline de Dados em Tempo Real na AWS

## 📌 Visão Geral

Este projeto implementa uma arquitetura de dados em tempo real utilizando serviços da AWS, combinando processamento **streaming** e **batch**.

O objetivo é demonstrar a construção de um pipeline moderno capaz de:

- Ingerir dados em tempo real  
- Processar eventos continuamente  
- Gerar alertas automáticos  
- Armazenar dados estruturados para análise  

---

## 🏗️ Arquitetura

A solução segue uma abordagem híbrida:

### 🔹 Camada de Streaming (Tempo Real)
- API → AWS Lambda (Producer)  
- Amazon Kinesis (Data Stream)  
- AWS Lambda (Consumer)  
- Amazon SNS (Alertas via notificação)  

### 🔹 Camada Batch (Data Lake)
- Amazon S3 (camadas raw e gold)  
- AWS Glue (Crawler + Data Catalog + ETL)  
- Amazon Athena (consulta analítica)  

---

## 🔄 Fluxo de Dados

1. Dados são enviados via API  
2. Uma função Lambda envia os eventos para o Kinesis  
3. O Kinesis distribui os dados em tempo real  
4. Outra Lambda processa os eventos  
5. Alertas são disparados via SNS  
6. Os dados são armazenados no S3 (raw)  
7. O Glue cataloga e transforma os dados  
8. Dados tratados são armazenados no S3 (gold)  
9. O Athena permite consultas SQL para análise  

---

## 🧰 Tecnologias Utilizadas

- Amazon S3  
- AWS Glue  
- Amazon Athena  
- Amazon Kinesis  
- AWS Lambda  
- Amazon SNS  

---

## 📊 Antes vs Depois

### ❌ Antes
- Dados não estruturados  
- Ausência de processamento em tempo real  
- Nenhuma geração de alertas  
- Dificuldade de análise  

### ✅ Depois
- Pipeline estruturado e escalável  
- Processamento em tempo real  
- Geração de alertas automáticos  
- Data Lake organizado (raw → gold)  
- Análise via SQL com Athena  

---

## 📸 Evidências do Projeto

As evidências estão disponíveis na pasta:
