# White Paper

## Postal Trust

Infraestrutura blockchain open source para serviços postais e logística, com blockchain permissionada e IA nativa para rastreabilidade, cadeia de custódia e interoperabilidade entre operadores.

## Status do documento

Versão: `0.1-draft`

Data: `2026-05-12`

Licença sugerida para o documento: `CC BY 4.0`

Status atual:

- documento conceitual inicial;
- aberto a comentários, crítica técnica e contribuições da comunidade;
- sujeito a revisões arquiteturais conforme a evolução do repositório.

## Resumo

O setor postal e logístico ainda opera com rastreamento fragmentado, baixa interoperabilidade entre empresas, disputa recorrente sobre custódia e grande dependência de processos manuais para validação documental, conciliação e auditoria. Este white paper propõe o `Postal Trust`, uma plataforma open source baseada em blockchain permissionada e inteligência artificial nativa, desenhada para permitir rastreabilidade auditável, cadeia de custódia verificável, automação contratual e integração federada entre operadores.

O projeto adota uma abordagem `self-hosted first`: cada empresa pode operar sua própria instância e sua própria rede permissionada, mantendo controle sobre dados sensíveis e regras operacionais. Ao mesmo tempo, a plataforma nasce com um protocolo aberto para permitir interoperabilidade futura entre instâncias, formando uma camada federada de confiança entre organizações do ecossistema postal e logístico.

A blockchain é usada como mecanismo de imutabilidade, prova e coordenação. A IA é usada como camada de leitura, classificação, automação, explicação, detecção de anomalias e apoio à decisão. O objetivo não é criar apenas mais um sistema de rastreamento, nem uma blockchain genérica para logística, mas uma infraestrutura aberta que una `confiança criptográfica`, `operação empresarial`, `privacidade by design` e `inteligência operacional`.

## 1. O problema

Sistemas logísticos atuais tendem a apresentar pelo menos cinco limitações estruturais:

1. `Rastreamento fragmentado`
Cada operador registra eventos em sua própria base, com formatos e semânticas distintas, o que dificulta visibilidade ponta a ponta.

2. `Ausência de cadeia de custódia auditável`
Nem sempre existe prova forte, padronizada e imutável sobre quem detinha a responsabilidade pelo objeto em determinado momento.

3. `Baixa interoperabilidade`
Integrações entre empresas costumam ser caras, lentas e dependentes de contratos bilaterais específicos.

4. `Processos manuais excessivos`
Documentos, comprovantes, exceções e disputas ainda exigem grande carga de trabalho humano.

5. `Dificuldade de conciliação entre verdade operacional e verdade jurídica`
Uma informação pode existir em um sistema, mas ser difícil de provar, auditar ou reconciliar diante de uma disputa.

## 2. A tese do projeto

O `Postal Trust` parte da seguinte tese:

> A logística multioperador precisa de uma camada aberta de confiança e interoperabilidade, na qual blockchain garanta integridade e custódia, enquanto IA reduza fricção operacional, acelere análise e amplie a capacidade de decisão.

Em vez de assumir que uma blockchain pública irrestrita resolverá o problema por si só, o projeto adota uma estratégia mais pragmática:

- blockchain permissionada por instância;
- software open source;
- operação self-hosted;
- protocolo aberto para federação;
- IA nativa desde o primeiro dia;
- privacidade e conformidade como requisitos centrais.

## 3. Objetivos

O projeto busca atingir os seguintes objetivos:

1. criar uma trilha imutável e verificável de eventos logísticos;
2. padronizar a transferência de custódia entre participantes;
3. ancorar documentos e evidências de forma auditável;
4. permitir automação de regras operacionais e financeiras;
5. oferecer APIs e SDKs para integração com sistemas empresariais;
6. usar IA para leitura documental, classificação, explicação, risco e suporte operacional;
7. permitir que organizações operem de forma independente e interoperável;
8. fomentar uma comunidade open source em torno de um protocolo aberto.

## 4. Princípios de design

### 4.1 Blockchain com função clara

A blockchain deve resolver problemas reais de integridade, custódia, prova e automação. Ela não deve ser usada apenas como substituta genérica de banco de dados.

### 4.2 Self-hosted first

A primeira proposta de valor precisa ser útil para uma única empresa. O projeto não deve depender de adesão massiva inicial para funcionar.

### 4.3 Federação por padrão aberto

Cada instância deve ser capaz de conversar com outras usando um protocolo comum, sem exigir um operador central único.

### 4.4 Privacidade by design

Dados pessoais, comerciais sensíveis e anexos completos devem permanecer fora da chain sempre que possível.

### 4.5 IA nativa, mas auditável

A IA deve participar do fluxo desde o início, mas suas saídas precisam ser controláveis, observáveis e revisáveis.

### 4.6 Governança antes de escala

Regras de participação, validação, confiança e arbitragem devem ser desenhadas antes da expansão para redes multiempresa mais abertas.

## 5. Escopo do sistema

O `Postal Trust` propõe uma infraestrutura para:

- identidade digital de remessas;
- rastreamento de eventos;
- cadeia de custódia;
- vinculação de documentos e evidências;
- automação por smart contracts;
- integração por API;
- relatórios e copilotos com IA;
- federação futura entre empresas e parceiros.

O projeto não parte da premissa de substituir toda a logística existente. Em vez disso, ele atua como `camada de confiança e interoperabilidade` sobre processos e sistemas já existentes.

## 6. Arquitetura de alto nível

O desenho da plataforma é organizado em camadas.

### 6.1 Camada blockchain

Responsável por:

- ledger distribuído;
- registro de eventos críticos;
- transferência de custódia;
- ancoragem de hashes;
- execução de smart contracts;
- validação e consenso entre nós autorizados.

### 6.2 Camada de domínio logístico

Responsável por:

- remessas;
- itens ou lotes;
- eventos;
- custódias;
- exceções;
- entregas;
- devoluções.

### 6.3 Camada documental

Responsável por:

- armazenamento off-chain;
- referências criptográficas;
- comprovantes;
- notas fiscais;
- invoices;
- anexos de auditoria;
- artefatos de compliance.

### 6.4 Camada financeira

Responsável por:

- split por etapa;
- garantias operacionais;
- conciliação;
- bônus e penalidades;
- liquidação contratual;
- **PostalCoin** como unidade de valor nativa para precificação e liquidação por trecho (ver [documento dedicado](POSTAL_COIN.md)).

### 6.5 Camada de IA

Responsável por:

- OCR e extração documental;
- classificação de eventos;
- resumo de remessas;
- detecção de inconsistências;
- explicação de decisões;
- suporte conversacional;
- análise de risco e fraude.

### 6.6 Camada de integração

Responsável por:

- APIs;
- webhooks;
- filas e eventos;
- SDKs;
- adaptadores para ERP, TMS, WMS e sistemas legados;
- interoperabilidade entre instâncias.

## 7. Blockchain permissionada como fundação

O projeto assume desde o início que a melhor arquitetura para o problema é uma `blockchain permissionada`, e não uma cadeia pública irrestrita.

### 7.1 Motivos

1. melhor controle de participação e escrita;
2. maior aderência à LGPD e sigilo empresarial;
3. menor custo operacional;
4. melhor previsibilidade de performance;
5. compatibilidade com ambientes corporativos;
6. caminho mais realista para adoção.

### 7.2 Consenso

Os mecanismos mais coerentes para o projeto são:

- `Proof of Authority`;
- `BFT permissionado`;
- variantes de `DPoS permissionado`.

`Proof of Work` não é prioridade, por não ser adequado ao perfil de throughput, latência e custo esperado para logística empresarial.

### 7.3 Estrutura de nós

Uma instância pode operar com nós distribuídos entre:

- matriz;
- filiais;
- hubs logísticos;
- parceiros homologados;
- auditor independente;
- seguradora ou entidade de garantia, quando aplicável.

## 8. O que vai e o que não vai on-chain

### 8.1 Recomendado on-chain

- IDs pseudonimizados;
- criação da remessa;
- eventos críticos;
- transferências de custódia;
- hashes de documentos;
- referências contratuais;
- estados de workflow;
- marcos de liquidação;
- saldos, transações e eventos da PostalCoin (via Layer 2).

### 8.2 Recomendado off-chain

- dados pessoais em claro;
- endereços completos;
- documentos integrais;
- fotos e vídeos completos;
- anexos pesados;
- telemetria extensa;
- informações comerciais sensíveis não essenciais para prova imutável.

## 9. IA nativa desde o primeiro dia

A IA não entra como chatbot decorativo. Ela faz parte da proposta estrutural do sistema.

### 9.1 Funções da IA

1. `Interpretar`
Ler documentos, mensagens, comprovantes e contexto operacional.

2. `Classificar`
Organizar eventos, exceções, riscos e incidentes.

3. `Explicar`
Gerar relatórios, sumários, justificativas e descrições operacionais.

4. `Detectar`
Apontar anomalias, divergências, fraude e inconsistências.

5. `Apoiar`
Atuar como copiloto para operadores, integradores, analistas e auditores.

6. `Prever`
Antecipar risco de atraso, ruptura, falha documental ou disputa.

### 9.2 Guardrails

O projeto deve adotar desde o início:

- trilha de auditoria para automações relevantes;
- controle de acesso a dados usados em prompts;
- revisão humana para decisões críticas;
- políticas de mascaramento e minimização de dados;
- capacidade de desligar fluxos de IA sem interromper o núcleo operacional.

### 9.3 Regra central

> A IA interpreta. A blockchain prova. A governança decide.

### 9.4 PostalCoin — O Selo Programável

O ecossistema Postal Trust prevê a introdução futura da **PostalCoin**, um ativo digital de utilidade (Utility Token) lastreado na capacidade operacional logística. A PostalCoin funciona como um **Real World Asset (RWA)** — a evolução do selo postal para um selo programável.

Princípios fundamentais:

- emissão baseada em **Proof of Infrastructure**: tokens emitidos com base na capacidade logística auditada de operadores federados;
- **liquidação automática por trecho**: cada etapa da cadeia consome e libera tokens conforme confirmação de custódia;
- **incentivos inteligentes**: teoria dos jogos para otimizar rotas ineficientes e incentivar crowdshipping na última milha;
- **slashing de performance**: penalidades automáticas para operadores que falham em prazos ou integridade;
- **Layer 2 dedicada**: infraestrutura de alto throughput para transações financeiras com taxas próximas de zero.

A PostalCoin não é uma criptomoeda especulativa. É a unidade de valor operacional do protocolo, projetada como evolução futura após a consolidação das funcionalidades operacionais básicas.

> Para a tese completa, consulte o [documento dedicado da PostalCoin](POSTAL_COIN.md).

## 10. Privacidade, segurança e conformidade

Privacidade e conformidade não são anexos do projeto. São parte do desenho fundamental.

### 10.1 Privacidade

Medidas base:

- pseudonimização;
- criptografia;
- segregação on-chain e off-chain;
- minimização de dados;
- controle de acesso por papel;
- logs de consulta e manipulação.

### 10.2 LGPD

O projeto deve ser concebido para reduzir exposição de dados pessoais na camada imutável. O foco da chain deve ser a prova do evento e não a publicação irrestrita do dado.

### 10.3 Segurança

Medidas esperadas:

- assinatura criptográfica de eventos;
- rotação de credenciais;
- autenticação forte;
- trilha de auditoria;
- gestão de segredos;
- validação de integridade documental;
- políticas de revogação e suspensão de participantes.

## 11. Governança

O modelo de governança precisa existir tanto no nível local quanto no federado.

### 11.1 Governança por instância

Cada instância define:

- quem pode operar como validador;
- quem pode registrar eventos;
- políticas de onboarding;
- políticas de auditoria;
- níveis de permissão;
- resposta a incidentes;
- regras de suspensão e revogação.

### 11.2 Governança federada

Em redes interoperáveis, será necessário definir:

- padrões de confiança cruzada;
- protocolos de assinatura;
- semântica comum de eventos;
- arbitragem de disputas;
- critérios de homologação entre instâncias.

## 12. Modelo de adoção

O caminho de adoção mais realista não é convencer o mercado inteiro a entrar numa única rede desde o dia 1. O caminho é:

1. uma empresa adota internamente;
2. integra parceiros próximos;
3. padroniza eventos e cadeia de custódia;
4. conecta-se a outras instâncias;
5. participa de uma federação mais ampla.

Isso reduz barreira de entrada e aumenta chance de validação progressiva.

## 13. Casos de uso prioritários

Os contextos mais promissores para as primeiras validações são:

1. `Objetos de alto valor`
Maior necessidade de prova, custódia e auditoria.

2. `Operações cross-border`
Maior complexidade documental e multiator.

3. `Cadeias multimodais`
Maior risco de fragmentação de rastreamento.

4. `Seguros e sinistros`
Maior valor da prova de integridade e responsabilidade.

5. `Operações com muitos terceiros`
Maior necessidade de interoperabilidade e governança.

## 14. MVP proposto

O MVP deve ser pequeno o suficiente para ser construído e forte o suficiente para demonstrar a tese.

### 14.1 Capacidades mínimas

- rede blockchain permissionada local;
- criação de remessas;
- identificador físico simples, como QR;
- registro de eventos principais;
- transferência de custódia;
- anexação de documentos com hash on-chain;
- API básica;
- painel administrativo;
- OCR documental;
- resumo de remessa por IA;
- relatório básico de auditoria.

### 14.2 Eventos mínimos

- criação;
- coleta;
- entrada em hub;
- saída de hub;
- transferência de custódia;
- entrega;
- exceção.

### 14.3 Objetivo do MVP

Provar que a plataforma consegue unir:

- rastreamento estruturado;
- prova imutável;
- IA útil no fluxo operacional;
- base para interoperabilidade futura.

## 15. Roadmap de evolução

### Fase 1 - Fundação

- domínio e modelo de dados;
- ledger permissionado;
- API inicial;
- documentos hasheados;
- painel inicial;
- IA documental.

### Fase 2 - Custódia e automação

- custódia assinada;
- smart contracts básicos;
- copiloto operacional;
- trilhas de auditoria;
- análise de risco inicial.

### Fase 3 - Financeiro e compliance

- split e conciliação;
- garantias;
- módulos de disputa;
- compliance documental ampliado.

### Fase 4 - Federação

- protocolo entre instâncias;
- interoperabilidade padronizada;
- roteamento entre empresas;
- conciliação entre redes.

### Fase 5 - Ecossistema aberto

- SDKs maduros;
- adaptadores comunitários;
- marketplace de integrações;
- governança federada mais ampla;
- possível ancoragem pública opcional.

### Evolução futura — PostalCoin

- introdução da PostalCoin como unidade de valor do ecossistema;
- smart contracts de escrow e liquidação por trecho;
- Proof of Infrastructure para emissão;
- oráculos IoT para precificação dinâmica;
- marketplace de capacidade logística;
- crowdshipping incentivado por tokens.

## 16. Open source e comunidade

Este projeto nasce com vocação aberta. Isso significa que a comunidade pode contribuir não apenas com código, mas também com:

- revisão do protocolo;
- validação da modelagem de eventos;
- crítica de segurança;
- contribuições de SDK;
- conectores para sistemas legados;
- melhorias de IA;
- revisão jurídica e de privacidade;
- exemplos de implantação;
- casos de uso setoriais.

### 16.1 Áreas prioritárias para contribuição

1. especificação de eventos logísticos;
2. modelo de custódia e prova;
3. armazenamento documental e hashing;
4. consenso e governança permissionada;
5. SDKs de integração;
6. observabilidade e auditoria;
7. fluxos de IA com guardrails.

### 16.2 Filosofia de colaboração

O projeto deve buscar:

- transparência arquitetural;
- interoperabilidade acima de lock-in;
- padrões simples e extensivos;
- contribuições revisáveis;
- documentação forte;
- preocupação real com segurança e privacidade.

## 17. Limitações e riscos

Este white paper reconhece alguns riscos importantes:

1. `Escopo excessivo`
Blockchain, IA, integração, governança e compliance juntos podem inflar o projeto.

2. `Adoção lenta`
Empresas podem hesitar em adotar novas camadas de confiança sem casos comprovados.

3. `Risco de complexidade desnecessária`
Se a blockchain for usada em partes que não exigem imutabilidade, o sistema pode ficar mais pesado do que deveria.

4. `Risco de automação mal governada`
IA sem guardrails pode introduzir erro, viés ou exposição de dados.

5. `Desafio federado`
A interoperabilidade entre instâncias pode ser tecnicamente e institucionalmente mais difícil do que parece.

## 18. Conclusão

O `Postal Trust` propõe uma nova base para sistemas postais, de rastreamento e cadeia de custódia: uma base em que blockchain não é discurso, mas mecanismo de prova; e em que IA não é enfeite, mas ferramenta operacional nativa.

O projeto se posiciona entre dois extremos:

- de um lado, sistemas centralizados com baixa interoperabilidade;
- do outro, blockchains públicas genéricas pouco aderentes à operação empresarial.

A proposta é construir uma terceira via:

> uma infraestrutura open source, permissionada, federada e AI-native para coordenação logística confiável.

Se bem executado, o projeto pode servir como base para empresas, integradores, operadoras, pesquisadores e comunidade open source desenvolverem um novo padrão de rastreabilidade auditável e interoperabilidade logística.

## 19. Próximos passos sugeridos

1. revisar este white paper com a comunidade;
2. definir o nicho inicial do MVP;
3. escolher a stack técnica da blockchain permissionada;
4. definir o modelo inicial de eventos e custódia;
5. iniciar a estrutura do repositório com documentação, contratos de dados e protótipos;
6. abrir issues para contribuições de arquitetura, segurança, IA e protocolo;
7. revisar a [tese da PostalCoin](POSTAL_COIN.md) como evolução futura do ecossistema.
