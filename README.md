<div align="center">
🏥 Idoso+
Painel de Monitoramento de Saúde para Idosos
utilizando Inteligência Artificial e Computação em Nuvem com AWS
---
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![AI](https://img.shields.io/badge/Inteligência_Artificial-blueviolet?style=for-the-badge&logo=openai&logoColor=white)
![Serverless](https://img.shields.io/badge/Serverless-FD5750?style=for-the-badge&logo=serverless&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge)
<br/>
> *"A tecnologia a serviço de quem mais precisa de cuidado."*
<br/>
🌐 Acesse o MVP →   |   📋 Trello do Projeto →
</div>
---
📖 Sobre o Projeto
O Idoso+ é um painel inteligente e acessível de monitoramento de saúde para idosos, desenvolvido como Projeto Final do programa AWS re/Start + IA da Escola da Nuvem. A plataforma combina Computação em Nuvem com AWS, Inteligência Artificial generativa e uma interface acessível por voz e texto para apoiar idosos, familiares e profissionais de saúde.
O projeto nasce como resposta ao acelerado envelhecimento populacional no Brasil: em 2023, pela primeira vez, o número de brasileiros com 60+ anos superou a faixa de 15 a 24 anos. Até 2070, os idosos devem representar 37,8% da população.
---
🎯 O Problema
Muitos idosos precisam de lembretes para medicamentos, atividades físicas e consultas. Familiares nem sempre conseguem monitorar diariamente, o que aumenta riscos de:
😔 Isolamento social
🧠 Esquecimentos frequentes (especialmente de medicamentos)
🚨 Riscos de saúde não monitorados
---
💡 A Solução
O Idoso+ oferece uma plataforma web responsiva (e futuramente mobile) com:
Funcionalidade	Descrição
🩺 Registro de Sinais Vitais	Pressão arterial, frequência cardíaca e oxigenação
💊 Lembretes de Medicação	Alertas sonoros e visuais por nome e horário
📅 Agendamento de Consultas	Calendário integrado de compromissos médicos
📔 Diário de Bem-Estar	Registro de humor, dor, sono, apetite e atividades
🤖 Análise com IA	Sugestões geradas por inteligência artificial com base nos registros
🆘 Botão de Emergência (SOS)	Alerta imediato para familiares e cuidadores
👨‍👩‍👦 Painel para Familiares	Acompanhamento remoto do histórico do idoso
---
👥 Equipe — Equipe 7
Nome	GitHub	Contribuição Principal
Adalto Reis	@adalto	Infraestrutura AWS & Demo MVP
Elisangela Santos	@elisangela	Requisitos Funcionais & Documentação
Evandro Silva	@evanbms	💻 Desenvolvimento Técnico do MVP
Guilherme Gomes	@guilherme	Pesquisa, Ideação & Metodologia Ágil
Jéssica Viana	@jessicaviana	Liderança, Backlog & Arquitetura
> 📌 **Orientador:** Rafael Santos — Escola da Nuvem  
> 🎓 **Turma:** C8 | BRSAO-200 (Noite) | Dezembro de 2025
---
🚀 MVP
O MVP foi desenvolvido por Evandro Silva e já está disponível no GitHub Pages:
🔗 https://evanbms.github.io/idosoplus/
O MVP é um Painel de Monitoramento de Saúde web responsivo que inclui:
Registro de sinais vitais
Lembretes de medicação com horários
Agendamento de consultas médicas
Diário de bem-estar (humor, dor, sono, apetite, atividades)
Análise automatizada com IA baseada nos dados do diário
> ⚕️ *O painel não substitui o acompanhamento médico profissional, mas funciona como apoio ao autocuidado.*
---
🏗️ Arquitetura AWS (Serverless)
A solução utiliza uma arquitetura serverless na região `us-east-1`, desenhada para alta disponibilidade, escalabilidade e segurança de dados sensíveis de saúde.
```
Usuários (Android/iOS/Web)
        │
        ▼
 Amazon CloudFront  ←→  AWS WAF
        │
        ▼
 Amazon Amplify (Frontend)
        │
        ▼
Amazon API Gateway
        │
        ▼
   AWS Lambda (Orquestração)
   ┌────┴────────────────────────────────┐
   │                                     │
   ▼                                     ▼
Amazon DynamoDB                    Amazon S3
(dados do usuário)            (áudios e arquivos)
   │                                     │
   ▼                                     ▼
 Eventos                        Amazon Transcribe
EventBridge                     (áudio → texto)
Scheduler                              │
   │                                   ▼
   ▼                          Amazon Comprehend Medical
Amazon SNS/SES                  (análise clínica NLP)
(notificações)                         │
                                       ▼
                               Amazon Lex (chatbot)
                                       │
                                       ▼
                           Amazon Bedrock — Claude
                             (análise cognitiva / IA)
                                       │
                                       ▼
                              Amazon Polly (voz TTS)
```
🔐 Segurança & Conformidade (LGPD)
Camada	Serviço	Função
Autenticação	Amazon Cognito + Rekognition	Login com biometria facial
Proteção	AWS WAF	Bloqueio de ataques (SQLi, XSS, DDoS)
Auditoria	AWS CloudTrail	Registro de todas as ações
Segredos	AWS Secrets Manager	Chaves e tokens seguros
Permissões	AWS IAM	Acesso mínimo por função
📊 Observabilidade
Serviço	Uso
Amazon CloudWatch	Logs, métricas e alarmes
AWS X-Ray	Rastreamento de execuções (tracing)
Amazon Systems Manager	Operações e automação
---
🧩 Diagrama de Containers
O projeto é organizado em 6 containers funcionais:
```
┌─────────────────────────────────────────────────────────────┐
│                    Interface do Usuário                     │
│              AWS Lambda  │  Amazon S3 (áudio)               │
└────────────────────────────┬────────────────────────────────┘
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
    ┌──────────────┐ ┌──────────────┐ ┌──────────────────┐
    │ Diário de    │ │Acessibilidade│ │ Processamento/IA │
    │ Bem-Estar    │ │& Notificação │ │                  │
    │              │ │              │ │ Lambda           │
    │ Lambda       │ │ Polly (voz)  │ │ Amazon Lex       │
    │ Transcribe   │ │ Chat / UI    │ │ Comprehend Med.  │
    │ DynamoDB     │ │ SNS / SES    │ │ Bedrock (Claude) │
    │ S3           │ │              │ │                  │
    └──────────────┘ └──────────────┘ └──────────────────┘
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
    ┌──────────────┐ ┌──────────────┐ ┌──────────────────┐
    │ Comunicação  │ │  Segurança   │ │  Monitoramento   │
    │              │ │              │ │                  │
    │ SNS (SMS)    │ │ IAM          │ │ CloudWatch       │
    │ SES (e-mail) │ │ CloudTrail   │ │ X-Ray            │
    └──────────────┘ └──────────────┘ └──────────────────┘
```
---
🛠️ Tecnologias Utilizadas
<details>
<summary><strong>☁️ AWS — Infraestrutura & Backend</strong></summary>
AWS Lambda — Lógica serverless e orquestração
Amazon API Gateway — Endpoints REST seguros
Amazon DynamoDB — Banco NoSQL (perfis, diários, lembretes)
Amazon S3 — Armazenamento de áudios e arquivos
Amazon EventBridge Scheduler — Agendamento de lembretes
Amazon SQS (DLQ) — Fila de reprocessamento de erros
Amazon SNS / SES — Notificações push, SMS e e-mail
</details>
<details>
<summary><strong>🤖 AWS — Inteligência Artificial</strong></summary>
Amazon Transcribe — Conversão de voz em texto (PT-BR)
Amazon Comprehend Medical — Extração de entidades clínicas
Amazon Lex — Motor de chatbot (intenções e comandos)
Amazon Bedrock (Claude) — Análise cognitiva e respostas empáticas
Amazon Polly — Síntese de voz (TTS) para acessibilidade
</details>
<details>
<summary><strong>🔐 AWS — Segurança & Identidade</strong></summary>
Amazon Cognito — Autenticação e perfis de usuário
Amazon Rekognition — Biometria facial (login)
AWS WAF — Web Application Firewall
AWS IAM — Controle de acesso com privilégio mínimo
AWS Secrets Manager — Gestão de segredos
AWS CloudTrail — Auditoria completa
</details>
<details>
<summary><strong>📡 AWS — Entrega & Observabilidade</strong></summary>
Amazon Amplify — Hospedagem do frontend
Amazon CloudFront — CDN global
Amazon CloudWatch — Métricas, logs e alarmes
AWS X-Ray — Tracing de execuções
Amazon Systems Manager — Operações automatizadas
</details>
---
📋 Metodologia Ágil
O projeto foi organizado com Kanban no Trello, dividido em 3 sprints:
Sprint	Foco	Status
Sprint 1	Planejamento e definição do problema	✅ Concluído
Sprint 2	Requisitos, MVP e Evoluções Futuras	✅ Concluído
Sprint 3	Testes, validação com usuários reais e entrega final	✅ Concluído
📋 Ver quadro no Trello
---
🔭 Evoluções Futuras
[ ] 📊 Relatórios e gráficos de evolução clínica
[ ] 🌿 Guia de Nutrição Saudável (cardápios para diabéticos e hipertensos)
[ ] 📡 Integração com IoT (medidor de glicose, smartwatch, aparelho auditivo)
[ ] 🔒 Criptografia avançada com AWS KMS
[ ] 🏋️ Recomendações de exercícios físicos semanais
[ ] 🤝 Sugestões de socialização
[ ] 🩺 Comunicação direta com profissionais de saúde
[ ] 🤖 Suporte a robôs cuidadores e entregas por drones
[ ] 👁️ Login com biometria facial e digital
[ ] 🎙️ Comandos de voz para toda a interface
---
🏛️ Pilares do AWS Well-Architected Framework
Pilar	Implementação
⚡ Eficiência de Performance	Serverless com Lambda + DynamoDB on-demand
🔒 Segurança	WAF + Cognito + IAM + CloudTrail + Secrets Manager
🏗️ Confiabilidade	Alta disponibilidade nativa (multi-AZ) dos serviços gerenciados
💰 Otimização de Custos	Pay-per-use com Lambda; sem servidores ociosos
🌱 Sustentabilidade	Recursos provisionados sob demanda, sem ociosidade
🔧 Excelência Operacional	CloudWatch + X-Ray + runbooks + CI/CD
---
📁 Estrutura do Repositório
```
idosoplus/
├── 📄 README.md
├── 📂 docs/
│   ├── Documento_de_Entrega_Final.pdf
│   ├── Apresentacao_Slides.pdf
│   ├── Arquitetura_AWS.png
│   ├── Diagrama_de_Containers.png
│   └── Backlog_de_Tarefas.png
├── 📂 mvp/                          ← desenvolvido por @evanbms
│   └── (ver: evanbms/idosoplus)
└── 📂 assets/
    └── screenshots/
```
> 💡 **O código-fonte do MVP está no repositório do Evandro:**  
> 🔗 **[github.com/evanbms/idosoplus](https://github.com/evanbms/idosoplus)**
---
🌟 Feedback do Professor
> *"Em primeiro lugar, quero parabenizá-los pela entrega do projeto final. O documento de vocês ficou bem estruturado e completo. Quanto à apresentação em si, ficou **excelente**. Houve um equilíbrio perfeito entre o tempo de fala de cada membro da equipe e o uso de recursos visuais... a maneira como vocês escolheram mostrar o diagrama, com zoom in e zoom out de cada elemento, facilitou muito o entendimento. A demo prática ficou simples, clara e objetiva e a decisão de terminar com os vídeos de IA trouxe o tipo de impacto que é necessário para o final de uma apresentação de sucesso."*
>
> — **Rafael Santos**, Instrutor — Escola da Nuvem, 2025
---
📚 Referências
IBGE — Censo 2023: idosos superam jovens de 15 a 24 anos
ONU — Dia Internacional das Pessoas Idosas 2025
AWS Lambda | Amazon Bedrock | Amazon Lex
Amazon Polly | Amazon Comprehend Medical
Amazon DynamoDB | AWS WAF
---
📜 Licença
Este projeto foi desenvolvido para fins acadêmicos no programa AWS re/Start + IA da Escola da Nuvem (Turma C8 | BRSAO-200 | Noite | 2025).
---
<div align="center">
Feito com ❤️ pela Equipe 7 — Escola da Nuvem · AWS re/Start + IA · 2025
Adalto Reis · Elisangela Santos · Evandro Silva · Guilherme Gomes · Jéssica Viana
</div>
