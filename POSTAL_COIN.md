# PostalCoin — O Selo Programável

## Ecossistema PostalCoin: A Evolução do Selo para um Ativo Digital Logístico

### Status do documento

Versão: `0.1-draft`

Data: `2026-05-12`

Licença sugerida para o documento: `CC BY 4.0`

Status atual:

- documento conceitual inicial;
- aberto a comentários, crítica técnica e contribuições da comunidade;
- sujeito a revisões conforme a evolução do repositório e do white paper principal.

---

## 1. Resumo

O projeto PostalCoin propõe a criação de um **ativo digital de utilidade (Utility Token)** lastreado na capacidade operacional logística. Diferente de uma criptomoeda comum, a PostalCoin funciona como um **Real World Asset (RWA)**, onde cada token representa o direito de transporte e processamento de carga, auditado e executado via Smart Contracts.

A PostalCoin é a evolução conceitual do selo postal: de um comprovante de pagamento físico e estático para um **selo programável**, capaz de carregar regras de liquidação, incentivos dinâmicos, penalidades automáticas e rastreabilidade financeira de ponta a ponta.

Dentro do ecossistema Postal Trust, a PostalCoin resolve um problema estrutural: **como remunerar de forma justa, transparente e automática cada participante de uma cadeia logística multioperador, proporcionalmente ao esforço real de cada etapa**.

> A PostalCoin não é uma criptomoeda especulativa. É a unidade de valor operacional do protocolo Postal Trust.

---

## 2. Tese Central

A logística tradicional opera com faturamento manual, repasses lentos e disputas recorrentes sobre custo e responsabilidade entre operadores. A PostalCoin propõe substituir esse modelo por uma **liquidação financeira em tempo real**, governada por smart contracts e alimentada por dados operacionais reais.

A tese central é:

> Transformar a empresa postal de uma transportadora rígida em um **Orquestrador de Malha Logística**, onde cada trecho, cada operador e cada entrega é precificado, executado e liquidado de forma programável, auditável e automática.

Essa transformação se apoia em três pilares:

1. **lastro real**: tokens emitidos com base na capacidade logística auditada, não em especulação;
2. **liquidação por trecho**: cada etapa da cadeia consome e libera tokens conforme confirmação de custódia;
3. **incentivos inteligentes**: teoria dos jogos aplicada para otimizar rotas ineficientes e incentivar a última milha.

---

## 3. Arquitetura de Emissão (Tokenomics)

### 3.1 Proof of Infrastructure (Prova de Infraestrutura)

A emissão da PostalCoin é baseada em um modelo inovador chamado **Proof of Infrastructure**: operadores logísticos federados emitem tokens com base na sua capacidade operacional auditada.

Diferente de Proof of Work (esforço computacional) ou Proof of Stake (capital travado), o Proof of Infrastructure ancora a emissão na **capacidade real de mover carga no mundo físico**.

Critérios de emissão:

- capacidade de processamento auditada (ex: kg/dia, objetos/dia);
- cobertura geográfica comprovada;
- infraestrutura operacional verificada (hubs, veículos, equipes);
- histórico de performance e compliance;
- score de reputação no ecossistema.

> Exemplo: um operador com capacidade auditada de processar 10.000 kg/dia em rotas de até 500 km pode emitir tokens proporcionais a essa capacidade.

### 3.2 Emissão Algorítmica

O protocolo regula a oferta circulante de acordo com o volume de entregas realizadas com sucesso, evitando a inflação do ativo sem contrapartida física.

Regras:

- a emissão é proporcional à capacidade auditada;
- tokens só entram em circulação quando há operação correspondente;
- o protocolo ajusta a oferta com base na demanda real;
- operadores com score de reputação mais alto podem ter limites de emissão maiores;
- operadores com slashing recorrente têm limites reduzidos automaticamente.

### 3.3 Quem Pode Emitir

- **Operadores federados**: emissão direta, baseada na sua infraestrutura auditada;
- **Parceiros autorizados**: podem mintar tokens se autorizados pelo protocolo e pelo operador federado que os homologou;
- **Entidades não autorizadas**: não podem emitir.

### 3.4 Unicidade do Token

A PostalCoin é **uma só moeda** em todo o ecossistema Postal Trust. Não existe uma moeda por instância ou por operador. Todas as instâncias federadas compartilham o mesmo token, garantindo interoperabilidade financeira nativa.

---

## 4. Mecânica Operacional e Liquidação Automática

O sistema substitui o faturamento manual por uma **liquidação financeira em tempo real**, executada por smart contracts.

### 4.1 Ciclo Completo

```
Remetente compra PostalCoins
        │
        ▼
Posta objeto → Smart Contract retém valor total (escrow)
        │
        ▼
Coleta confirmada → operador de coleta recebe sua fração
        │
        ▼
Triagem confirmada → hub recebe sua fração
        │
        ▼
Trânsito confirmado → transportador recebe sua fração
        │
        ▼
Last mile confirmada → entregador recebe sua fração
        │
        ▼
Entrega confirmada → escrow zerado, liquidação concluída
```

### 4.2 Pagamento por Trecho

O valor da postagem é "travado" em um contrato inteligente no momento da criação da remessa. À medida que o objeto passa pelos **gatilhos logísticos** (Coleta → Triagem → Hub → Trânsito → Distribuição → Entrega), frações do token são liberadas automaticamente para os executores de cada etapa.

Cada liberação é condicionada à **confirmação de custódia** registrada na blockchain:

- assinatura digital do operador;
- timestamp do evento;
- localização autorizada;
- evidências associadas (quando aplicável).

### 4.3 Exemplo Prático

Remessa: 5 kg, São Paulo → Interior de Minas Gerais

| Etapa | Operador | Esforço | PostalCoin |
|-------|----------|---------|------------|
| Coleta | Operador A (SP) | Baixo | 8 PCN |
| Triagem | Hub SP | Baixo | 5 PCN |
| Trânsito SP→MG | Transportadora B | Alto | 42 PCN |
| Last mile (interior MG) | Crowdshipper local | Alto | 30 PCN |
| **Total retido em escrow** | | | **85 PCN** |

---

## 5. Oráculos e Precificação Dinâmica

### 5.1 Oráculos de Preço

Sensores, sistemas de monitoramento e dados operacionais atuam como **oráculos**, informando ao smart contract o custo real para que o valor em tokens seja ajustado dinamicamente.

Fontes de dados dos oráculos:

- **IoT e sensores**: GPS, NFC, leitores de código, balanças;
- **Custo de combustível**: integração com bases de preço atualizadas;
- **Demanda**: volume de remessas na rota no período;
- **Sazonalidade**: ajustes por datas de pico (Black Friday, Natal, etc.);
- **Condições operacionais**: clima, restrições de trânsito, greves.

### 5.2 Fórmula de Esforço (proposta)

```
esforço_rota = (
    peso_distância    × distância_km
  + peso_modal        × fator_modal
  + peso_objeto       × (peso_kg + volume_m³)
  + peso_complexidade × fator_documental
  + peso_risco        × score_risco
  + peso_prazo        × fator_urgência
  + peso_demanda      × fator_sazonalidade
)

custo_pcn = esforço_rota × taxa_base_pcn
```

Cada operador de cada etapa recebe uma fração proporcional ao seu esforço relativo dentro do esforço total da rota.

---

## 6. Incentivos de Mercado e Crowdshipping

A PostalCoin utiliza a **teoria dos jogos** para otimizar rotas ineficientes e incentivar a participação de operadores em regiões de difícil acesso.

### 6.1 Sinalização por Preço

Trechos de baixa densidade logística (ex: interior de MG, regiões remotas do Norte) apresentam um **custo maior em PostalCoins**, gerando incentivo financeiro para que micro-operadores locais ou crowdshippers realizem a entrega da "última milha".

O mecanismo é simples:

- rota com poucos operadores → preço maior em PCN → atrai novos operadores;
- rota com muitos operadores → preço se estabiliza → equilíbrio de mercado.

### 6.2 Entrega por Densidade

O protocolo permite a criação de **tarifas diferenciadas** para quem opta por aguardar a consolidação de carga:

- entrega expressa: custo cheio;
- entrega econômica: o remetente aceita aguardar consolidação, pagando menos PCN;
- entrega agrupada: objetos para a mesma região são consolidados, reduzindo custo unitário.

Esse modelo otimiza o frete e reduz a pegada de carbono.

### 6.3 Crowdshipping

Qualquer pessoa ou microempresa pode se cadastrar como **crowdshipper** em regiões onde o custo de última milha é alto. O incentivo em PostalCoins torna viável a entrega em locais onde operadores tradicionais não atuam de forma rentável.

---

## 7. Smart Contracts da PostalCoin

### 7.1 Contratos Principais

| Contrato | Função |
|----------|--------|
| **Emissão** | Mintar tokens com base na capacidade auditada do operador federado |
| **Escrow** | Reter o valor total da postagem até a conclusão da cadeia logística |
| **Liberação por etapa** | Liberar fração proporcional ao operador que confirmou custódia |
| **Penalidade (Slashing)** | Debitar tokens do operador que falhou em prazo ou integridade |
| **Reembolso** | Devolver tokens ao remetente em caso de extravio ou falha total |
| **Bônus por SLA** | Premiar operadores que superem metas de prazo e qualidade |
| **Queima** | Retirar tokens de circulação em casos definidos pela governança |

### 7.2 Regras de Execução

- liberação de tokens só ocorre após confirmação de custódia na blockchain;
- slashing é automático e não depende de disputa manual;
- reembolso pode ser parcial (proporcional ao trecho não executado);
- bônus por SLA é financiado por uma fração reservada do escrow;
- todos os contratos são auditáveis e determinísticos.

---

## 8. Governança e Qualidade (Slashing)

### 8.1 Slashing de Performance

Se um operador falha nos prazos ou na integridade da carga (verificada via rastro digital e oráculos IoT), o protocolo executa um **slashing automático**:

- tokens são retirados do operador faltoso;
- tokens são devolvidos ao remetente como **multa automática**;
- o score de reputação do operador é reduzido;
- reincidência pode levar à suspensão da capacidade de emissão.

### 8.2 Score de Reputação

O rastro de transações na blockchain cria um **histórico imutável de eficiência** para cada centro de distribuição e parceiro logístico.

Fatores do score:

- taxa de entregas no prazo;
- taxa de integridade da carga;
- frequência de slashing;
- volume operacional;
- tempo de resposta;
- qualidade de evidências de custódia.

O score afeta diretamente:

- limites de emissão de tokens;
- prioridade na alocação de rotas;
- visibilidade no marketplace de operadores;
- elegibilidade para bônus por SLA.

---

## 9. Infraestrutura Técnica

### 9.1 Layer 2 / Subnet Dedicada

Para viabilizar o volume de transações diárias de um ecossistema logístico (potencialmente milhões de eventos por dia), o projeto prevê a utilização de uma **Layer 2 ou Subnet dedicada**, garantindo:

- taxas de transação próximas de zero;
- alta velocidade de processamento;
- compatibilidade com a blockchain permissionada principal;
- isolamento de carga transacional financeira.

### 9.2 Integração com a Blockchain Principal

A Layer 2 da PostalCoin opera em paralelo à blockchain principal do Postal Trust:

- **blockchain principal**: registra eventos de custódia, provas e auditoria;
- **Layer 2 PostalCoin**: processa transações financeiras, escrow, liberações e slashing;
- **ancoragem periódica**: estados financeiros consolidados são ancorados na chain principal para auditabilidade.

---

## 10. Privacidade e Compliance

### 10.1 LGPD e Dados Financeiros

O tratamento de dados financeiros da PostalCoin segue os mesmos princípios de privacidade by design do Postal Trust:

- saldos individuais são pseudonimizados;
- transações são registradas com IDs opacos;
- dados pessoais associados a carteiras ficam off-chain;
- relatórios financeiros são acessíveis apenas por papéis autorizados.

### 10.2 Dados On-chain vs Off-chain

| On-chain (Layer 2) | Off-chain |
|---------------------|-----------|
| Saldos pseudonimizados | Dados pessoais do titular |
| Transações de escrow | Detalhes comerciais sensíveis |
| Liberações por etapa | Documentos fiscais completos |
| Eventos de slashing | Relatórios gerenciais |
| Emissões e queimas | Dados de integração com ERP |
| Score de reputação | Contratos comerciais |

### 10.3 Nota Regulatória

> [!WARNING]
> Dependendo da jurisdição, mesmo tokens utilitários internos podem exigir análise jurídica específica. Este documento descreve a visão conceitual e técnica do token. A análise regulatória formal para cada mercado é um passo necessário antes da implementação e fica fora do escopo deste documento.

---

## 11. Impacto Estratégico

A implementação da PostalCoin transforma a empresa postal de uma **transportadora rígida** em um **Orquestrador de Malha Logística**. Isso permite:

### 11.1 Redução de Custos Fixos

Regiões remotas que hoje exigem estrutura fixa e cara podem ser atendidas via **parcerias automáticas** com crowdshippers e micro-operadores incentivados por PostalCoins.

### 11.2 Antecipação de Receita (Hedge Logístico)

Grandes e-commerces podem **comprar PostalCoins antecipadamente** a um preço fixo, garantindo custo de frete previsível para operações futuras. Isso funciona como um hedge logístico, protegendo contra flutuações de custo de transporte.

### 11.3 Transparência Absoluta

O rastreamento físico e financeiro de cada objeto postado é **unificado**: quem moveu, quando moveu, quanto custou e quem foi pago — tudo auditável na mesma infraestrutura.

### 11.4 Marketplace de Capacidade

O ecossistema pode evoluir para um **marketplace aberto de capacidade logística**, onde operadores ofertam capacidade e remetentes buscam as melhores rotas e preços, tudo liquidado em PostalCoins.

---

## 12. Riscos

### 12.1 Riscos Técnicos

- complexidade de integração entre Layer 2 e blockchain principal;
- calibração dos oráculos de preço e esforço;
- volume transacional exigindo infraestrutura robusta;
- segurança dos smart contracts de escrow e slashing.

### 12.2 Riscos Operacionais

- resistência de operadores tradicionais ao modelo de slashing;
- dificuldade de auditoria de capacidade para Proof of Infrastructure;
- calibração inicial dos pesos de esforço por rota;
- onboarding de crowdshippers em regiões remotas.

### 12.3 Riscos Regulatórios

- classificação do token por órgãos reguladores (CVM, Banco Central);
- necessidade de compliance específico por jurisdição;
- tratamento tributário das transações em PostalCoin;
- relação com legislação de meios de pagamento.

### 12.4 Riscos de Adoção

- necessidade de massa crítica de operadores para o modelo funcionar;
- curva de aprendizado para remetentes e operadores;
- competição com modelos de faturamento tradicionais;
- percepção de complexidade desnecessária.

---

## 13. Roadmap da PostalCoin

A PostalCoin é uma **evolução futura** do ecossistema Postal Trust, prevista para depois da consolidação das funcionalidades operacionais básicas.

### Fase Conceitual (atual)

- documentação da tese e do modelo econômico;
- revisão pela comunidade;
- definição de parâmetros iniciais de esforço e emissão.

### Fase de Pesquisa

- estudo de viabilidade técnica da Layer 2;
- modelagem matemática da emissão algorítmica;
- simulação de cenários de crowdshipping;
- análise regulatória por jurisdição.

### Fase de Protótipo

- smart contracts de escrow e liberação por etapa;
- integração com oráculos simulados;
- testes de slashing e reputação;
- painel de gestão de PostalCoins.

### Fase de Piloto

- operação com operadores reais em rotas controladas;
- validação da precificação dinâmica;
- ajuste de parâmetros de esforço;
- feedback de remetentes e operadores.

### Fase de Produção

- integração completa com o ecossistema Postal Trust;
- marketplace de capacidade;
- crowdshipping em escala;
- governança descentralizada do token.

---

## 14. Relação com o Projeto Postal Trust

A PostalCoin não substitui nem compete com o Postal Trust. Ela é uma **camada econômica** que se integra ao ecossistema existente:

- o **Postal Trust** provê rastreabilidade, custódia, auditoria e IA;
- a **PostalCoin** provê liquidação, incentivos, reputação e economia de rede.

Juntos, formam uma infraestrutura completa para logística programável:

> Confiança criptográfica + Inteligência operacional + Economia de rede.

---

## Documentos Relacionados

- [White Paper do Postal Trust](WHITEPAPER.md)
- [Blueprint do Projeto](PROJECT_BLUEPRINT.md)
- [Obsidian Brain](OBSIDIAN_BRAIN.md)
- [Guia de Contribuição](CONTRIBUTING.md)
- [English version](POSTAL_COIN_EN.md)
