README.mk

# Projeto: Arquiteturas AWS para Processamento de Arquivos

## Descrição
Este projeto apresenta duas arquiteturas distintas utilizando serviços da AWS para ingestão, processamento e armazenamento de arquivos. Os diagramas ilustram abordagens serverless e baseadas em EC2, com foco em escalabilidade, segurança e automação.

## Arquitetura 1 – Serverless com S3, Lambda e DynamoDB

### Componentes
- Sistema de Arquivos
- AWS CLI
- Amazon S3
- AWS Lambda (Java, Python, .NET Core)
- Amazon DynamoDB

### Fluxo
1. Arquivo enviado via AWS CLI para o S3.
2. Trigger aciona Lambda.
3. Lambda processa o arquivo.
4. Dados são gravados no DynamoDB.

### Vantagens
- Baixo custo
- Alta escalabilidade
- Sem servidor

## Arquitetura 2 – EC2 com EBS e RDS

### Componentes
- Usuário
- Amazon EC2
- Amazon EBS (Volumes D e E)
- Amazon RDS

### Fluxo
1. Usuário envia arquivo para EC2.
2. EC2 armazena em EBS.
3. Processamento local.
4. Dados persistidos no RDS.

### Vantagens
- Controle total do ambiente
- Ideal para aplicações legadas

## Comparativo

| Item             | Serverless (S3+Lambda+DynamoDB) | EC2 (EBS+RDS)         |
|------------------|----------------------------------|------------------------|
| Execução         | Lambda (event-driven)            | EC2 (manual)           |
| Armazenamento    | S3 + DynamoDB                    | EBS + RDS              |
| Escalabilidade   | Alta                             | Moderada               |
| Custo            | Baixo                            | Potencialmente alto    |
| Complexidade     | Baixa                            | Alta                   |

## Requisitos
- Conta AWS com permissões para S3, Lambda, EC2, EBS e RDS
- AWS CLI configurado
- IAM Roles para execução segura

## Autor
Alex – Custódia, PE, Brasil
