<sub>🇺🇸 [English version](README.md)</sub>

# Olá, eu sou o Túlio 👋

Desenvolvedor full-stack. Construo produtos do zero até a produção: banco de dados, back-end,
web, mobile e as integrações que fazem o negócio girar (pagamentos, WhatsApp, IA).

**Stack principal:** TypeScript · Node.js · Next.js · React Native (Expo) · Flutter · PostgreSQL / Supabase · GraphQL

> Os repositórios dos meus produtos são privados. Abaixo está o que cada um faz e o que eu
> resolvi neles. Mostro o código com prazer numa conversa.

---

## 🗓️ Qiki — agendamento por WhatsApp para salões e barbearias

SaaS em que a cliente marca, remarca e cancela horário conversando com um robô no WhatsApp,
e o salão acompanha tudo por um painel web.

<p align="center"><img src="assets/qiki.gif" width="260" alt="Cliente marcando horário com o robô do Qiki no WhatsApp"></p>

**Stack:** Next.js · TypeScript · Node.js · PostgreSQL (Supabase) · WhatsApp Cloud API (Meta) · Asaas · OpenAI

- **Multi-tenant seguro:** isolamento entre salões em duas camadas no PostgreSQL (Row Level
  Security + chaves estrangeiras compostas), provado por testes de integração e de intrusão
  (OWASP ZAP).
- **Robô de conversa:** motor de conversa puro e testável; a IA ajuda a entender a mensagem, mas
  disponibilidade e gravação do horário nunca dependem dela.
- **Sem agendamento duplicado:** constraint de exclusão no Postgres, testada sob concorrência real.
- **Pagamentos:** assinatura recorrente (cartão e Pix) com webhooks idempotentes, estorno
  automático e tratamento de chargeback.
- **Segurança web:** CSP com nonce, proteção contra SSRF e open redirect, rate limiting e captcha.
- **LGPD:** exclusão do titular em uma transação, retenção automática de dados e logs sem dados
  pessoais.
- Página pública de agendamento, lembretes, lista de espera, oferta de horários vagos e
  sincronização com Google Agenda.

**Status:** app aprovado pela Meta, em preparação para o lançamento.

---

## 🦫 Cashtor — finanças pessoais sem ansiedade

App de controle financeiro para Android, iOS e web, com o Beto, um assistente de IA que responde
perguntas como "quanto gastei com alimentação este mês?".

<p align="center">
  <img src="assets/cashtor-inicio.gif" width="220" alt="Tela inicial do Cashtor com saldo, orçamentos e movimentações">
  <img src="assets/cashtor-metas.gif" width="220" alt="Metas e sonhos no Cashtor">
  <img src="assets/cashtor-beto.gif" width="220" alt="Beto, o assistente de IA, resumindo os gastos do mês">
</p>

**Stack:** React Native (Expo) · TypeScript · Supabase (Postgres, Auth, Edge Functions) · OpenAI

- Contas, cartões de crédito com ciclo de fatura e parcelas, categorias, metas e contas fixas.
- **Importação de fatura por foto:** a IA lê a imagem e o app monta os lançamentos.
- **Modo família:** finanças compartilhadas, com acesso só por convite.
- **Segurança e privacidade:** chave da IA fora do app (Edge Function com JWT), limite de uso de
  IA por usuário, RLS, bloqueio por biometria, modo que esconde os valores, exclusão de conta
  com todos os dados e backup noturno do banco.
- Kill switches remotos para desligar recursos de IA sem publicar nova versão.

**Status:** em fase de publicação na Play Store.

---

## 🏪 Fluxy — gestão de loja e ponto de venda *(em desenvolvimento)*

Sistema de gestão para varejo: produtos, estoque, vendas, clientes, fornecedores e crediário.

**Stack:** Flutter (Android, web e desktop) · GraphQL (Apollo Server) · Node.js · MongoDB · SQLite

- **Funciona offline:** banco local (SQLite) com serviço de sincronização com o servidor.
- Leitura de código de barras, checkout, crédito da loja e pedidos de compra.
- Relatório de estoque com exportação em CSV e Excel.
- Uma base de código para celular, navegador e desktop, com layout responsivo e tema claro e escuro.

**Próximos passos:** emissão de NF-e, comissão de vendedores e mais relatórios.

---

📫 **Contato:** [tsalmeida1988@gmail.com](mailto:tsalmeida1988@gmail.com) · [LinkedIn](https://www.linkedin.com/in/tulio-almeida/)
