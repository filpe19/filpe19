# Relatório da Rodada 2 do Portfólio GitHub

Data: 2026-08-27

## Criado

- `acai-finance-case-study`  
  Estudo de caso público: https://github.com/filpe19/acai-finance-case-study

- `tickiton-case-study`  
  Estudo de caso público: https://github.com/filpe19/tickiton-case-study

- `jornada-contabil-case-study`  
  Estudo de caso público: https://github.com/filpe19/jornada-contabil-case-study

- `finance-ai-case-study`  
  Estudo de caso público: https://github.com/filpe19/finance-ai-case-study

Cada repositório foi criado como um estudo de caso limpo, sem clonar ou publicar o histórico Git dos projetos privados.

## Atualizado

- `filpe19/filpe19`:
  - Portfolio reorganizado por classes de problema de engenharia, não por framework.
  - Links públicos para Açaí Finance, TickiTon, Jornada Contábil, Club Pass Belém e Finance AI.
  - `ats` removido da seção principal de destaque.
  - Nota explícita sobre a próxima lacuna: um repositório público independente com código avaliável.
  - Conteúdo convertido para português, alinhado à língua nativa do perfil.

- `club-pass-belem-case-study`:
  - README padronizado com a estrutura dos novos cases.
  - Narrativa preservada: assinatura, pagamento, ativação, QR Code, validação, parceiros e iOS.
  - Posicionamento iOS mantido de forma honesta: experiência prática em app real, sem inflar senioridade.
  - Conteúdo convertido para português.

- Novos case studies:
  - READMEs em português.
  - Diagramas Mermaid.
  - Seções de arquitetura, fluxo de produto, stack, backend, dados, integrações, segurança, desafios, testes, infraestrutura e produção.

## Segurança

Abordagem usada nesta rodada:

- Repositórios de estudo de caso criados do zero.
- Nenhum histórico `.git` privado foi copiado.
- Nenhum código-fonte proprietário foi publicado.
- Nenhum `.env`, dump de banco, arquivo de credencial, chave SSH, certificado, dado de cliente ou URL de produção foi publicado.
- Capturas de tela não foram adicionadas a Açaí Finance, TickiTon, Jornada Contábil ou Finance AI porque o material disponível pode conter dados operacionais, participantes, clientes, lojistas ou informações financeiras.
- Capturas de tela existentes do Club Pass foram mantidas porque já estavam sanitizadas e passaram por varredura com `strings`.
- `gitleaks` e `trufflehog` não estavam instalados localmente; por isso foi usada varredura precisa com `rg`/`git grep`.

Padrões verificados:

- Tokens GitHub.
- Valores com formato semelhante a Mercado Pago.
- Valores com formato semelhante a Telegram/API token.
- Chaves cloud.
- Valores com formato de JWT.
- Blocos de chave privada.
- Formatos comuns de tokens SendGrid/Slack.
- Atribuições de `password`, `secret`, `token`, `api_key`, `access_key` e `private_key`.

Cobertura:

- Arquivos atuais de cada repositório público.
- Histórico alcançável por `git rev-list --all`.
- Branches e tags.
- Saída `strings` dos PNGs existentes do Club Pass.

Resultado:

- Nenhum valor com padrão de secret foi encontrado nos repositórios públicos de estudo de caso.
- Cada novo repositório público possui apenas a branch `main` e nenhuma tag.

## Cases Públicos

- Açaí Finance: SaaS / Multi-tenant / Marketplace / Pagamentos  
  https://github.com/filpe19/acai-finance-case-study

- TickiTon: Bilheteria / Eventos / Pagamentos / Sistemas Transacionais  
  https://github.com/filpe19/tickiton-case-study

- Jornada Contábil: Infraestrutura de Evento / Comércio / Pagamentos / Produção  
  https://github.com/filpe19/jornada-contabil-case-study

- Club Pass Belém: Assinaturas / QR Code / Pagamentos / iOS  
  https://github.com/filpe19/club-pass-belem-case-study

- Finance AI: IA / Telegram / Automação / Assistente Financeiro  
  https://github.com/filpe19/finance-ai-case-study

## Codebases Privadas

Os repositórios comerciais originais permanecem privados:

- `acaifinace`
- `tickiton`
- `jornada-contabil-fiscal`
- `clubpassbelem`
- `assistenteia-finance`

## Repositórios Fixados

Ordem recomendada para pins:

1. `acai-finance-case-study`
2. `tickiton-case-study`
3. `jornada-contabil-case-study`
4. `club-pass-belem-case-study`
5. `finance-ai-case-study`
6. Deixar vazio até existir um repositório público mais forte com código avaliável.

Não fixar `ats`.

Status atual:

- A consulta GraphQL `pinnedItems` para `filpe19` retornou lista vazia.
- A API/CLI disponível neste ambiente não expôs mutação para fixar repositórios no perfil.
- Portanto, os pins não foram configurados automaticamente.

Ação manual necessária:

1. Abrir https://github.com/filpe19 logado na conta.
2. Na área de repositórios fixados, clicar em `Customize your pins`.
3. Selecionar:
   - `acai-finance-case-study`
   - `tickiton-case-study`
   - `jornada-contabil-case-study`
   - `club-pass-belem-case-study`
   - `finance-ai-case-study`
4. Não selecionar `ats`.
5. Salvar os pins.

Isso substitui a apresentação automática de "Popular repositories" e remove o `ats` da vitrine principal sem deletar o repositório ou alterar sua visibilidade.

## Recomendação de Repositório Público com Código

Ainda existe uma lacuna de avaliação direta de código, porque os principais sistemas de produção devem permanecer privados.

Repositório futuro recomendado:

`transactional-platform-api`

Escopo sugerido:

- API Laravel.
- Autenticação e autorização.
- Domínio de pedidos/pagamentos.
- Inbox de webhooks com idempotência.
- Ledger append-only ou trilha de auditoria.
- Migrations e seeders MySQL.
- Testes unitários e de feature.
- Validação e tratamento de erros.
- Filas/events quando fizer sentido.
- Workflow de CI.
- Ambiente local com Docker.
- Documentação de arquitetura.

Esse projeto deve ser independente, inspirado em padrões arquiteturais dominados, sem copiar propriedade intelectual comercial.

## Teste de Recrutador

**Um recrutador acessando `github.com/filpe19` por cerca de 30 segundos consegue identificar os principais sistemas reais que Felipe desenvolveu?**  
Sim. O perfil abre com posicionamento de engenharia e links para cinco estudos de caso de produtos reais.

**Fica evidente que são produtos e não exercícios?**  
Sim. Os cases mostram fluxos de produto, pagamentos, webhooks, validação por QR Code, assinaturas, operação de eventos, settlement de marketplace, painéis admin, runbooks de produção e testes.

**Fica evidente a diversidade entre SaaS, pagamentos, eventos, assinaturas, iOS e IA?**  
Sim. Cada projeto está posicionado pela classe de problema de engenharia, não por uma lista genérica de Laravel/PHP.

**Existe evidência suficiente de engenharia e produção?**  
Sim para arquitetura, entrega de produto e operação orientada à produção. Para revisão direta de código, o próximo passo recomendado é um repositório público independente com código, testes e CI.
