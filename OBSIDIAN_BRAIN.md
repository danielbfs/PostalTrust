# Obsidian Brain do Projeto

Este arquivo foi pensado para visualização no Obsidian com Mermaid. Ele mostra os principais blocos do sistema e como eles se comunicam.

## Mindmap Geral

```mermaid
mindmap
  root((Postal Trust))
    Visão
      Open source
      Self-hosted
      Federada
      API-first
      AI-native
    Blockchain
      Rede permissionada
      Nós validadores
      Consenso BFT ou PoA
      Ledger imutável
      Smart contracts
    IA
      OCR documental
      Classificação de eventos
      Resumo de remessas
      Detecção de fraude
      Copiloto operacional
      Relatórios automáticos
    Domínio
      Remessa
      Custódia
      Eventos
      Documentos
      Liquidação
      Compliance
    Integração
      API REST ou GraphQL
      Webhooks
      SDKs
      Protocolo federado
      ERP TMS WMS
    Privacidade
      LGPD
      Pseudonimização
      Dados off-chain
      Hashes on-chain
      Controle de acesso
    Aplicações
      Painel admin
      Portal auditoria
      App operador
      App transportador
      Chat IA
    Roadmap
      MVP
      Custódia
      Financeiro
      Federação
      Ecossistema
```

## Mapa de Comunicação Entre Blocos

```mermaid
flowchart TD
    A[Identidade da Remessa] --> B[Blockchain de Eventos]
    A --> C[Custódia e Provas]
    A --> E[Documentos e Evidências]

    B --> C
    B --> D[Smart Contracts]
    B --> G[Risco Fraude e Compliance]
    B --> I[Aplicações]

    C --> D
    C --> G
    C --> I

    E --> B
    E --> G
    E --> I

    D --> F[Financeiro e Liquidação]
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

    L[Federação entre Instâncias] --> H
    L --> B
    L --> C
    L --> D
    L --> F
```

## Fluxo Operacional Resumido

```mermaid
sequenceDiagram
    participant U as Usuário ou Empresa
    participant API as API Gateway
    participant ID as Identidade da Remessa
    participant DOC as Documentos
    participant AI as Camada de IA
    participant BC as Blockchain
    participant CU as Custódia
    participant SC as Smart Contracts
    participant FI as Financeiro

    U->>API: Criar remessa
    API->>ID: Gerar identidade digital
    U->>DOC: Enviar documentos
    DOC->>AI: Extrair e validar dados
    AI-->>DOC: Campos, alertas e classificação
    ID->>BC: Registrar criação
    API->>CU: Registrar coleta e custódia
    CU->>BC: Registrar evento assinado
    BC->>SC: Executar regras de negócio
    SC->>FI: Atualizar split ou garantia
    AI->>API: Resumir status e detectar exceções
    CU->>BC: Registrar entrega
    BC->>SC: Encerrar fluxo contratual
    SC->>FI: Liquidar pagamento final
```

## Leitura Rápida dos Blocos

- `Identidade da Remessa`: cria o ativo digital e o identificador físico.
- `Blockchain de Eventos`: guarda a trilha imutável principal.
- `Custódia e Provas`: registra a responsabilidade por etapa.
- `Smart Contracts`: executa regras de negócio e automação.
- `Documentos e Evidências`: guarda anexos off-chain e hashes on-chain.
- `Financeiro e Liquidação`: gerencia split, escrow e repasses.
- `Risco, Fraude e Compliance`: monitora integridade e políticas.
- `API e Protocolo Aberto`: conecta sistemas internos e outras instâncias.
- `Camada de IA Nativa`: apoia todos os blocos com leitura, análise e automação.
- `Privacidade e LGPD`: garante minimização, pseudonimização e controle de acesso.
- `Federação entre Instâncias`: permite interoperabilidade entre empresas.
