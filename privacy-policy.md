# Política de Privacidade

**Última atualização:** Junho de 2026

## 1. Introdução

A presente Política de Privacidade descreve como recolhemos, utilizamos, armazenamos e protegemos os dados pessoais dos utilizadores do **Ads AO** ("Plataforma"). Ao utilizar a Plataforma, o utilizador aceita os termos descritos neste documento.

Esta política está em conformidade com a legislação angolana aplicável, incluindo a Lei de Proteção de Dados Pessoais.

A Plataforma é de propriedade e operada pela **Techtri Labs**.

## 2. Dados que Recolhemos

### 2.1 Dados fornecidos diretamente pelo utilizador

- **Dados de Registo:** Nome completo, endereço de e-mail, número de telefone.
- **Dados de Autenticação Social:** Quando o utilizador opta por iniciar sessão com o Google, recolhemos o nome e e-mail associados à conta Google. Quando o utilizador conecta a sua conta do Facebook via Facebook OAuth, recolhemos o nome, e-mail e identificador da conta Facebook, bem como a lista de Páginas gerizadas.
- **Dados de Perfil e KYC:** Para planos pagos, recolhemos o NIF (Número de Identificação Fiscal), morada e, quando aplicável, documentos de identificação para verificação KYC (Know Your Customer).
- **Dados de Pagamento:** Histórico de transações, montantes em Kwanzas, referências de pagamento geradas pela **Provedora de Pagamentos**.
- **Dados de Campanhas:** Conteúdo dos anúncios (imagens, vídeos, textos, headlines, CTAs), URLs de destino, números de WhatsApp, definições de público-alvo (localização, idade, género, interesses).
- **Comunicações:** Mensagens enviadas para o suporte ou através dos canais de contacto da Plataforma.

### 2.2 Dados recolhidos automaticamente

- **Dados de Utilização:** Páginas visitadas, funcionalidades utilizadas, tempo de sessão, cliques e interações com a Plataforma.
- **Dados Técnicos:** Endereço IP, tipo de navegador, sistema operativo, dispositivo, idioma do navegador, fuso horário.
- **Dados de Desempenho de Anúncios:** Impressões, cliques, CTR, gasto total, métricas de campanhas sincronizadas via Meta Marketing API (Insights API).

### 2.3 Dados recebidos de terceiros

- **Meta (Facebook/Instagram):** Quando o utilizador conecta uma conta do Facebook ou uma Página, a Plataforma recebe dados autorizados via Facebook Login e Meta API, incluindo identificadores de conta, nome da Página, e permissões concedidas (`ads_management`, `ads_read`, `business_management`).
- **Google:** Nome e e-mail associados à conta Google quando o utilizador utiliza o Google OAuth para autenticação.
- **Provedora de Pagamentos:** Confirmação de pagamentos via webhook e polling, incluindo o estado da transação e o montante pago.

## 3. Finalidade do Tratamento de Dados

Utilizamos os dados recolhidos para as seguintes finalidades:

| Finalidade | Base Legal |
|---|---|
| Criar e gerir a conta do utilizador | Execução do contrato |
| Processar pagamentos e gerir saldo | Execução do contrato |
| Criar, publicar e gerir anúncios no Facebook e Instagram via Meta API | Execução do contrato |
| Sincronizar métricas de desempenho de anúncios | Execução do contrato |
| Enviar notificações sobre o estado de campanhas, pagamentos e alertas (e-mail, in-app) | Execução do contrato / Interesse legítimo |
| Verificar identidade para cumprimento KYC (planos pagos) | Obrigação legal |
| Emitir faturas e cumprir obrigações fiscais (SAFT/AFT) | Obrigação legal |
| Prevenir fraudes, abusos e dupla cobrança (idempotência) | Interesse legítimo |
| Monitorizar a segurança e disponibilidade da Plataforma | Interesse legítimo |
| Melhorar a Plataforma com base em dados de utilização agregados | Interesse legítimo |

## 4. Partilha de Dados com Terceiros

### 4.1 Subcontratantes (Processadores de Dados)

| Fornecedor | Serviço | Dados Partilhados | Localização |
|---|---|---|---|
| **Supabase** | Base de dados, autenticação, armazenamento | Todos os dados da Plataforma | Cloud (EUA/UE) |
| **Vercel** | Hospedagem e CDN | Dados de sessão e utilização | Cloud (EUA) |
| **Inngest** | Orquestração de tarefas em segundo plano | Dados de campanhas e transações para processamento assíncrono | Cloud (EUA) |
| **Sentry** | Monitorização de erros | Dados de navegação em caso de erro | Cloud (EUA) |
| **Provedora de Pagamentos** | Gateway de pagamento | Referências de pagamento, montantes em Kz | Angola |
| **Resend** | Envio de e-mails transacionais e notificações | Nome, e-mail, conteúdo da notificação | Cloud (EUA/UE) |

### 4.2 Plataformas de Anúncios (Meta)

A Plataforma atua como intermediária na gestão de anúncios. Para publicar anúncios, transmitimos os criativos e parâmetros de campanha para a Meta Platforms, Inc. (Facebook/Instagram) via Meta Marketing API. A Meta processa estes dados de acordo com a sua própria Política de Privacidade.

### 4.3 Requisitos Legais

Podemos divulgar dados pessoais quando exigido por lei, ordem judicial ou autoridade reguladora competente (ex.: AGT para efeitos fiscais, autoridades angolanas de proteção de dados).

## 5. Retenção de Dados

- **Dados de conta e perfil:** Mantidos enquanto a conta estiver ativa.
- **Dados de transações financeiras:** Conservados por um período mínimo de 10 anos, conforme requisitos legais e fiscais angolanos.
- **Dados de campanhas e métricas:** Conservados durante a vigência da conta, e por até 12 meses após o encerramento da conta.
- **Logs de auditoria:** Conservados por tempo indeterminado (append-only, imutáveis).
- **Dados de KYC e consentimento:** Conservados durante a vigência da conta e por até 5 anos após o encerramento, conforme requisitos legais.

Após o término dos períodos de retenção, os dados são permanentemente eliminados ou anonimizados através de processos automatizados.

## 6. Segurança dos Dados

Implementamos medidas técnicas e organizacionais para proteger os dados pessoais:

- **Encriptação em Trânsito:** Todas as comunicações utilizam HTTPS/TLS (Vercel e Supabase).
- **Encriptação em Repouso:** Dados sensíveis (NIF, telefone, documentos KYC) são encriptados com `pgsodium` (encriptação ao nível da coluna na base de dados).
- **Chaves de API:** Armazenadas exclusivamente no Supabase Vault, nunca em código-fonte ou variáveis de ambiente expostas no browser.
- **Row Level Security (RLS):** Isolamento de dados multi-tenant — cada utilizador apenas acede aos seus próprios dados.
- **Auditoria Imutável:** Todas as operações financeiras são registadas num log append-only.
- **Autenticação de Dois Fatores (2FA):** Obrigatória para contas de administrador.
- **Rate Limiting:** Proteção contra acessos abusivos nos endpoints críticos.
- **Verificação HMAC:** Validação de assinatura nos webhooks de pagamento da **Provedora de Pagamentos**.

## 7. Direitos do Titular dos Dados

O utilizador tem os seguintes direitos relativamente aos seus dados pessoais:

- **Direito de Acesso:** Solicitar uma cópia dos dados pessoais que mantemos.
- **Direito de Retificação:** Corrigir dados pessoais incompletos ou incorretos.
- **Direito de Eliminação:** Solicitar a eliminação dos dados pessoais (ver Secção 9 — Instruções de Exclusão de Dados).
- **Direito à Limitação do Tratamento:** Solicitar a restrição do tratamento dos dados em determinadas circunstâncias.
- **Direito de Portabilidade:** Receber os dados pessoais num formato estruturado e de uso corrente.
- **Direito de Oposição:** Opor-se ao tratamento de dados baseado em interesses legítimos.

Para exercer qualquer um destes direitos, o utilizador deve contactar-nos através do e-mail indicado na Secção 12.

Responderemos a todas as solicitações no prazo máximo de 30 dias, em conformidade com a legislação aplicável.

## 8. Utilização de Dados do Facebook

Quando o utilizador conecta a sua conta do Facebook ou autoriza a Plataforma a gerir anúncios em seu nome através do modelo híbrido de agência, a Plataforma recebe e processa dados da conta Facebook do utilizador, incluindo:

- Identificador da conta Facebook
- Nome e e-mail associados à conta
- Páginas do Facebook geridas pelo utilizador (para servir de destino das campanhas)
- Métricas de desempenho de anúncios

Estes dados são utilizados exclusivamente para as finalidades descritas na Secção 3 e não são partilhados com terceiros não indicados nesta Política.

**Remoção de dados do Facebook:** O utilizador pode, a qualquer momento, remover a ligação entre a sua conta Facebook e a Plataforma. Consulte a Secção 9 para instruções detalhadas.

## 9. Exclusão de Dados do Utilizador

Os utilizadores podem solicitar a eliminação dos seus dados a qualquer momento. Consulte o documento **Instruções de Exclusão de Dados** disponível em:

[`Instruções de Exclusão de Dados`](./data-deletion.md)

## 10. Transferências Internacionais de Dados

A Plataforma utiliza fornecedores de infraestrutura cloud que podem processar dados fora de Angola. Asseguramos que todos os subcontratantes cumprem normas adequadas de proteção de dados (incluindo certificações SOC 2, ISO 27001, e cláusulas contratuais padrão quando aplicável).

## 11. Alterações a esta Política

Reservamo-nos o direito de atualizar esta Política de Privacidade periodicamente. As alterações serão comunicadas aos utilizadores através de:
- Notificação por e-mail com 15 dias de antecedência
- Aviso in-app na Plataforma
- Atualização da data de "Última atualização" no topo deste documento

A utilização continuada da Plataforma após a entrada em vigor das alterações constitui aceitação da política atualizada.

## 12. Contacto

Para questões relacionadas com esta Política de Privacidade, exercício de direitos sobre os dados, ou comunicações com o Encarregado de Proteção de Dados:

- **E-mail:** suporte@ads.ao
- **Telefone:** +244 935 087 761 

---

&copy; 2026 Techtri Labs. Todos os direitos reservados.
