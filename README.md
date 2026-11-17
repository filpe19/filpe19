# Felipe Souza

**Engenheiro de software full stack · Belém, Pará**

Construo sistemas que lidam com dinheiro e controle de acesso: bilheteria, assinaturas, SaaS multi-tenant, pagamentos e IA aplicada. Cuido do caminho inteiro, do modelo de dados ao deploy, e mantenho em produção os sistemas que entrego. Tenho dois apps iOS publicados na App Store.

A maior parte do meu código é de clientes e fica em repositórios privados. Os estudos de caso abaixo explicam arquitetura, decisões e resultados sem expor código ou dados de ninguém.

## Sistemas em produção

### TickiTon · bilheteria e eventos

Checkout com reserva de estoque, Pix e cartão via Mercado Pago, ingresso com QR Code assinado (HMAC-SHA256), portaria que funciona sem internet, painel do produtor e reembolsos. Web e app iOS nativo na mesma API.

No teste de carga, 500 compradores disputaram 300 vagas: 300 ingressos vendidos, nenhum a mais.

`PHP 8.2` `MySQL` `Mercado Pago` `Swift` `SwiftUI` `PHPUnit` `Docker` `Cloud Run`

[tickiton.com.br](https://tickiton.com.br) · [App Store](https://apps.apple.com/br/app/tickiton/id6824281845) · [Estudo de caso](https://github.com/filpe19/tickiton-case-study)

### Açaí Finance · SaaS multi-tenant e pagamentos

Plataforma para várias empresas de alimentação e varejo no mesmo sistema: catálogo público, pedidos, PDV, caixa, pagamentos Mercado Pago com split de marketplace e carteira com ledger append-only. O tenant é resolvido no backend e o middleware bloqueia acesso cruzado.

Migrei a produção do Google Cloud para uma VPS com 7 minutos de janela. O tempo de resposta caiu de 0,3–0,9 s para cerca de 0,13 s.

`PHP 8.2` `React` `Vite` `MySQL 8` `Mercado Pago` `Docker` `Nginx`

[acaifinance.com.br](https://acaifinance.com.br) · [Estudo de caso](https://github.com/filpe19/acai-finance-case-study)

### Nix · assistente financeiro com IA

Assistente no WhatsApp e no Telegram: a pessoa conta o que gastou, por texto ou áudio, e ele mantém o registro, com relatórios, orçamentos e metas. O LLM só interpreta a intenção. Todo número sai de código determinístico sobre o banco, em centavos inteiros, e se o modelo cair o bot continua respondendo com os mesmos valores.

`Laravel 13` `PHP 8.4` `MySQL` `Redis` `Horizon` `whisper.cpp` `React 19`

[assistenteia.online](https://assistenteia.online) · [Estudo de caso](https://github.com/filpe19/finance-ai-case-study)

### ClubPass Belém · assinatura e acesso por QR Code

Uma assinatura que dá acesso a casas parceiras da noite de Belém. O acesso só é ativado depois do pagamento confirmado no Mercado Pago, o QR rotaciona e expira, e o validador confere a entrada pelo app.

`PHP 8.2` `React` `MySQL` `Swift` `SwiftUI` `AVFoundation` `Mercado Pago`

[App Store](https://apps.apple.com/br/app/clubpass-bel%C3%A9m/id6787500885) · [Estudo de caso](https://github.com/filpe19/club-pass-belem-case-study)

### Jornada Contábil Fiscal · plataforma de evento

Infraestrutura de um evento real da comunidade contábil: checkout autenticado com Asaas, inbox de eventos de pagamento com retry, portal do participante, check-in por QR, certificados, materiais privados, migração de dados legados e runbooks para o dia do evento.

`Laravel 13` `React 19` `TypeScript` `MySQL` `Asaas` `Playwright`

[jornadacontabilfiscal.com.br](https://jornadacontabilfiscal.com.br) · [Estudo de caso](https://github.com/filpe19/jornada-contabil-case-study)

### CRM Grupo Palace · operação comercial

Três sistemas para a mesma empresa de consórcios: CRM com pipeline, pós-venda, comissões e trilha de auditoria (permissões por perfil decididas no backend), landing page de captação e um ranking de vendas ao vivo para a TV do escritório.

`Laravel 13` `React` `MySQL 8` `NestJS` `Socket.io` `Next.js 16`

[Landing page](https://landingpage.crmpalace.com)

## Outros sistemas entregues

| Projeto | O que é | Stack |
|---|---|---|
| [Senshi Sushi](https://senshisushi.online/catalogo) | Operação de restaurante: garçom, cozinha, caixa, impressoras e maquininha Mercado Pago Point, mais catálogo com checkout online | Laravel 13, Inertia, React 19, MySQL |
| [Portal dos Urbanitários](https://urbanitariosdopara.org) | Saída do WordPress para Next.js com Payload CMS: 294 notícias e 1.310 anexos migrados e reconciliados, links antigos preservados com 301, 2FA próprio | Next.js 16, Payload CMS 3, PostgreSQL 17 |
| [Gama Silva Imóveis](https://gamasilvaimoveis.com.br) | Site imobiliário e painel de gestão na mesma aplicação, com métricas próprias sem cookies | Laravel 13, React 19, MySQL |
| [RK Story](https://rkstorys.com.br) | Catálogo de moda com painel de gestão e atendimento pelo WhatsApp | Laravel, Inertia, React |
| [Zorgmed](https://zorgmed.com.br) | Site institucional pré-renderizado para SEO, com deploy próprio | React, Vite, TypeScript |

## Código aberto e competições

| Projeto | Contexto | Links |
|---|---|---|
| **Amazônia Viva** | NASA Space Apps Challenge 2026, desafio *Harmonization of MODIS and VIIRS Hot Spots*. Transforma detecções de fogo por satélite em contexto territorial: histórico MODIS × VIIRS harmonizado, anomalias por município e quem pode ser afetado | [Demo](https://amazviva.online) · [Código](https://github.com/filpe19/amazonia-viva) |
| **JourneyOps** | Hackathon IBM Bob. O agente recebe a jornada real do usuário em vez de um ticket escrito à mão e corrige o bug que a suíte de testes verde não pegava. Sessões do agente congeladas por tag | [Demo](https://journeyops.tickiton.com.br) · [Código](https://github.com/filpe19/journeyops) |
| **Patrion** | Hackathon do TJPA, Desafio 2, feito em dupla. Inventário patrimonial com app offline-first, sincronização em lotes idempotentes e API com auditoria imutável | [Demo](https://patrion.online) |

## Palestra

**PHP aguenta o trampo?** · Ver-O-PHP, comunidade PHP de Belém, novembro de 2026. Arquitetura real da TickiTon: três portas de pagamento com uma única tranca, QR assinado com portaria offline e o laboratório de carga que mostrou onde estava o gargalo (no banco, não na linguagem).

## Como eu trabalho

- **Pagamentos que não perdem dinheiro.** Pix, cartão, assinatura recorrente, maquininha e split de marketplace com Mercado Pago, Asaas e Telegram Stars. Valor e taxa calculados no servidor, webhook tratado como evento repetível.
- **Transações sob concorrência.** Reserva atômica de estoque, ingresso emitido só após pagamento confirmado, check-in sem duplicidade e testes de carga com invariantes em SQL.
- **Autorização no backend.** Tenant, perfil e assinatura decididos no servidor. O frontend só reflete.
- **IA com os pés no chão.** O modelo entende linguagem natural e voz; números, saldos e projeções vêm de código que dá para testar.
- **Deploy com volta garantida.** Release atômica com symlink e rollback, backup antes de migration, Docker isolado em VPS compartilhada e runbooks escritos antes do dia do evento.
- **Testes que provam o fluxo.** PHPUnit, E2E com Playwright, webhook duplicado e corrida entre processos dentro da suíte, CI a cada push.

## Stack

**Backend:** PHP 8, Laravel 13, Node.js, NestJS, Python, FastAPI<br>
**Frontend:** React 19, TypeScript, Next.js 16, Inertia, Vite, Tailwind CSS<br>
**Mobile:** Swift, SwiftUI, Expo<br>
**Dados:** MySQL 8, PostgreSQL 17, SQLite, Redis<br>
**Pagamentos:** Mercado Pago (Pix, cartão, assinatura, Point), Asaas, Telegram Stars<br>
**Infraestrutura:** Docker, Nginx, PHP-FPM, Google Cloud Run, VPS Linux, GitHub Actions

## Contato

[felipealsouza17@gmail.com](mailto:felipealsouza17@gmail.com)
