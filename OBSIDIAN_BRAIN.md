# Obsidian Brain do Projeto

Este arquivo foi pensado para visualizacao no Obsidian com Mermaid. Ele mostra os principais blocos do sistema e como eles se comunicam.

## Mindmap Geral

```mermaid
mindmap
  root((Postal Trust))
    Visao
      Open source
      Self-hosted
      Federada
      API-first
      AI-native
    Blockchain
      Rede permissionada
      Nos validadores
      Consenso BFT ou PoA
      Ledger imutavel
      Smart contracts
    IA
      OCR documental
      Classificacao de eventos
      Resumo de remessas
      Deteccao de fraude
      Copiloto operacional
      Relatorios automaticos
    Dominio
      Remessa
      Custodia
      Eventos
      Documentos
      Liquidacao
      Compliance
    Integracao
      API REST ou GraphQL
      Webhooks
      SDKs
      Protocolo federado
      ERP TMS WMS
    Privacidade
      LGPD
      Pseudonimizacao
      Dados off-chain
      Hashes on-chain
      Controle de acesso
    Aplicacoes
      Painel admin
      Portal auditoria
      App operador
      App transportador
      Chat IA
    Roadmap
      MVP
      Custodia
      Financeiro
      Federacao
      Ecossistema
```

## Mapa de Comunicacao Entre Blocos

```mermaid
flowchart TD
    A[Identidade da Remessa] --> B[Blockchain de Eventos]
    A --> C[Custodia e Provas]
    A --> E[Documentos e Evidencias]

    B --> C
    B --> D[Smart Contracts]
    B --> G[Risco Fraude e Compliance]
    B --> I[Aplicacoes]

    C --> D
    C --> G
    C --> I

    E --> B
    E --> G
    E --> I

    D --> F[Financeiro e Liquidacao]
    D --> I

    F --> I
    F --> G

    G --> I

    H[API e Protocolo Aberto] --> A
    H --> B
    H --> C
    H --> E
    H --> F
    H --> I

    J[Camada de IA Nativa] --> A
    J --> B
    J --> C
    J --> D
    J --> E
    J --> F
    J --> G
    J --> H
    J --> I

    K[Privacidade e LGPD] --> A
    K --> B
    K --> C
    K --> E
    K --> H
    K --> I

    L[Federacao entre Instancias] --> H
    L --> B
    L --> C
    L --> D
    L --> F
```

## Fluxo Operacional Resumido

```mermaid
sequenceDiagram
    participant U as Usuario ou Empresa
    participant API as API Gateway
    participant ID as Identidade da Remessa
    participant DOC as Documentos
    participant AI as Camada de IA
    participant BC as Blockchain
    participant CU as Custodia
    participant SC as Smart Contracts
    participant FI as Financeiro

    U->>API: Criar remessa
    API->>ID: Gerar identidade digital
    U->>DOC: Enviar documentos
    DOC->>AI: Extrair e validar dados
    AI-->>DOC: Campos, alertas e classificacao
    ID->>BC: Registrar criacao
    API->>CU: Registrar coleta e custodia
    CU->>BC: Registrar evento assinado
    BC->>SC: Executar regras de negocio
    SC->>FI: Atualizar split ou garantia
    AI->>API: Resumir status e detectar excecoes
    CU->>BC: Registrar entrega
    BC->>SC: Encerrar fluxo contratual
    SC->>FI: Liquidar pagamento final
```

## Leitura Rapida dos Blocos

- `Identidade da Remessa`: cria o ativo digital e o identificador fisico.
- `Blockchain de Eventos`: guarda a trilha imutavel principal.
- `Custodia e Provas`: registra a responsabilidade por etapa.
- `Smart Contracts`: executa regras de negocio e automacao.
- `Documentos e Evidencias`: guarda anexos off-chain e hashes on-chain.
- `Financeiro e Liquidacao`: gerencia split, escrow e repasses.
- `Risco, Fraude e Compliance`: monitora integridade e politicas.
- `API e Protocolo Aberto`: conecta sistemas internos e outras instancias.
- `Camada de IA Nativa`: apoia todos os blocos com leitura, analise e automacao.
- `Privacidade e LGPD`: garante minimizacao, pseudonimizacao e controle de acesso.
- `Federacao entre Instancias`: permite interoperabilidade entre empresas.
