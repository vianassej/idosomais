# 🏥 Idoso+
### Painel de Monitoramento de Saúde para Idosos
**utilizando Inteligência Artificial e Computação em Nuvem com AWS**

![AWS](https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![IA](https://img.shields.io/badge/Intelig%C3%AAncia%20Artificial-8A2BE2?style=for-the-badge)
![Serverless](https://img.shields.io/badge/Serverless-FD5750?style=for-the-badge&logo=serverless&logoColor=white)
![Status](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen?style=for-the-badge)

> *"A tecnologia a serviço de quem mais precisa de cuidado."*

🌐 **[Acesse o MVP](https://evanbms.github.io/idosoplus/)** &nbsp;|&nbsp; 📋 **[Trello do Projeto](https://trello.com/b/zPIuGAgm/projeto-idoso-equipe-7)**

---

## 📖 Sobre o Projeto

O **Idoso+** é um painel inteligente e acessível de monitoramento de saúde para idosos, desenvolvido como **Projeto Final do programa AWS re/Start + IA** da [Escola da Nuvem](https://escoladanuvem.org/).

A plataforma combina **Computação em Nuvem com AWS**, **Inteligência Artificial generativa** e uma **interface acessível por voz e texto** para apoiar idosos, familiares e profissionais de saúde.

O projeto nasce como resposta ao acelerado **envelhecimento populacional** no Brasil: em 2023, pela primeira vez, o número de brasileiros com 60+ anos superou a faixa de 15 a 24 anos. Até 2070, os idosos devem representar **37,8% da população**.

---

## 🎯 O Problema

Muitos idosos precisam de lembretes para medicamentos, atividades físicas e consultas. Familiares nem sempre conseguem monitorar diariamente, o que aumenta riscos de:

- 😔 **Isolamento social**
- 🧠 **Esquecimentos frequentes** (especialmente de medicamentos)
- 🚨 **Riscos de saúde não monitorados**

---

## 💡 A Solução

| Funcionalidade | Descrição |
|---|---|
| 🩺 Registro de Sinais Vitais | Pressão arterial, frequência cardíaca e oxigenação |
| 💊 Lembretes de Medicação | Alertas sonoros e visuais por nome e horário |
| 📅 Agendamento de Consultas | Calendário integrado de compromissos médicos |
| 📔 Diário de Bem-Estar | Registro de humor, dor, sono, apetite e atividades |
| 🤖 Análise com IA | Sugestões geradas por inteligência artificial com base nos registros |
| 🆘 Botão de Emergência (SOS) | Alerta imediato para familiares e cuidadores |
| 👨‍👩‍👦 Painel para Familiares | Acompanhamento remoto do histórico do idoso |

---

## 👥 Equipe — Equipe 7

| Nome | GitHub | Contribuição Principal |
|---|---|---|
| **Adalto Reis** | [@adalto](https://github.com/) | Infraestrutura AWS & Demo MVP |
| **Elisangela Santos** | [@elisangela](https://github.com/) | Requisitos Funcionais & Documentação |
| **Evandro Silva** | [@evanbms](https://github.com/evanbms) | 💻 Desenvolvimento Técnico do MVP |
| **Guilherme Gomes** | [@guilherme](https://github.com/) | Pesquisa, Ideação & Metodologia Ágil |
| **Jéssica Viana** | [@jessicaviana](https://github.com/) | Liderança, Backlog & Arquitetura |

> 📌 **Orientador:** Rafael Santos — Escola da Nuvem
> 🎓 **Turma:** C8 | BRSAO-200 (Noite) | Dezembro de 2025

---

## 🚀 MVP

O MVP foi desenvolvido por **Evandro Silva** e está disponível em:

🔗 **https://evanbms.github.io/idosoplus/**

Inclui registro de sinais vitais, lembretes de medicação, agendamento de consultas, diário de bem-estar e análise automatizada com IA.

> ⚕️ *O painel não substitui o acompanhamento médico profissional, mas funciona como apoio ao autocuidado.*

---

## 🏗️ Arquitetura AWS (Serverless)

Arquitetura serverless na região `us-east-1`, com alta disponibilidade, escalabilidade e segurança para dados sensíveis de saúde.

**Fluxo principal:**

```
Usuários (Android / iOS / Web)
        │
   CloudFront + WAF
        │
   Amazon Amplify (Frontend)
        │
   Amazon API Gateway
        │
   AWS Lambda (Orquestração)
   ┌────┴──────────────────────────┐
   │                               │
DynamoDB + S3              Amazon Transcribe
(dados / arquivos)         (áudio → texto)
                                   │
                          Comprehend Medical
                           (análise clínica)
                                   │
                            Amazon Lex
                             (chatbot)
                                   │
                        Amazon Bedrock — Claude
                          (análise cognitiva)
                                   │
                           Amazon Polly
                            (voz / TTS)
```

---

## 🛠️ Tecnologias Utilizadas

**Infraestrutura & Backend**

![Lambda](https://img.shields.io/badge/AWS_Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white)
![DynamoDB](https://img.shields.io/badge/DynamoDB-4053D6?style=flat-square&logo=amazondynamodb&logoColor=white)
![S3](https://img.shields.io/badge/Amazon_S3-569A31?style=flat-square&logo=amazons3&logoColor=white)
![API Gateway](https://img.shields.io/badge/API_Gateway-FF4F8B?style=flat-square&logo=amazonapigateway&logoColor=white)

**Inteligência Artificial**

![Bedrock](https://img.shields.io/badge/Amazon_Bedrock_(Claude)-8A2BE2?style=flat-square)
![Transcribe](https://img.shields.io/badge/Amazon_Transcribe-FF9900?style=flat-square)
![Lex](https://img.shields.io/badge/Amazon_Lex-FF9900?style=flat-square)
![Polly](https://img.shields.io/badge/Amazon_Polly-FF9900?style=flat-square)
![Comprehend](https://img.shields.io/badge/Comprehend_Medical-FF9900?style=flat-square)

**Segurança & Identidade**

![Cognito](https://img.shields.io/badge/Amazon_Cognito-DD344C?style=flat-square)
![WAF](https://img.shields.io/badge/AWS_WAF-DD344C?style=flat-square)
![IAM](https://img.shields.io/badge/AWS_IAM-DD344C?style=flat-square)

**Observabilidade**

![CloudWatch](https://img.shields.io/badge/CloudWatch-FF4F8B?style=flat-square)
![XRay](https://img.shields.io/badge/X--Ray-FF4F8B?style=flat-square)
![CloudTrail](https://img.shields.io/badge/CloudTrail-FF4F8B?style=flat-square)

---

## 📋 Metodologia Ágil

Kanban com Trello, dividido em 3 sprints:

| Sprint | Foco | Status |
|---|---|---|
| Sprint 1 | Planejamento e definição do problema | ✅ Concluído |
| Sprint 2 | Requisitos, MVP e Evoluções Futuras | ✅ Concluído |
| Sprint 3 | Testes, validação com usuários e entrega final | ✅ Concluído |

---

## 🔭 Evoluções Futuras

- [ ] 📊 Relatórios e gráficos de evolução clínica
- [ ] 🌿 Guia de Nutrição Saudável
- [ ] 📡 Integração com IoT (glicosímetro, smartwatch)
- [ ] 🔒 Criptografia avançada com AWS KMS
- [ ] 🎙️ Comandos de voz para toda a interface
- [ ] 👁️ Login com biometria facial e digital
- [ ] 🤖 Suporte a robôs cuidadores

---

## 🌟 Feedback do Professor

> *"Ficou **excelente**. Houve um equilíbrio perfeito entre o tempo de fala de cada membro da equipe e o uso de recursos visuais... a maneira como vocês escolheram mostrar o diagrama facilitou muito o entendimento. A demo prática ficou simples, clara e objetiva e a decisão de terminar com os vídeos de IA trouxe o tipo de impacto que é necessário para o final de uma apresentação de sucesso."*
>
> — **Rafael Santos**, Instrutor — Escola da Nuvem, 2025

---

## 📜 Sobre

Projeto desenvolvido para o programa **AWS re/Start + IA** da **Escola da Nuvem**
Turma C8 | BRSAO-200 | Noite | 2025

**Equipe 7:** Adalto Reis · Elisangela Santos · Evandro Silva · Guilherme Gomes · Jéssica Viana
