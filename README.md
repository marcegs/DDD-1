# Dinâmica: Design Estratégico do Projeto

## Objetivo
Identificar os subdomínios do projeto, classificá-los (Core, Supporting, Generic) e desenhar os bounded contexts, incluindo suas interações. Esse exercício ajudará a criar uma visão clara e estratégica do domínio.

---

## 1. Nome do Projeto
**Colheita Digital**

---

## 2. Objetivo Principal do Projeto
**A proposta é criar uma plataforma onde pequenos empreendedores podem tokenizar partes de seus ativos produtivos ou de sua produção futura para captar recursos, e ao mesmo tempo, recompensar seus clientes com tokens de fidelidade que geram benefícios dentro de um ecossistema local.**  

---

## 3. Identificação dos Subdomínios
Liste os subdomínios do sistema e classifique-os como **Core Domain**, **Supporting Subdomain** ou **Generic Subdomain**.

| **Subdomínio**               | **Descrição**                                                                       | **Tipo**    |
| ---------------------------- | ----------------------------------------------------------------------------------- | ----------- |
| Gestão de Campanhas          | Gerenciamento de campanhas digitais.                                                | Core Domain |
| Cadastro de Usuários         | Gerencia o login, cadastro e permissões dos empreendedores e investidores.          | Supporting  |
| Pagamentos                   | Processa pagamentos.                                                                | Generic     |
| Gestão de benefícios         | Gerencia o pagamento de dividendos e/ou a emissão de token de créditos e benefícios | Core Domain |
| Relacionamento com parceiros | Gerencia o o relacionamento entre parceiros e clientes                              | Supporting  |

---

## 4. Desenho dos Bounded Contexts
Liste e descreva os bounded contexts identificados no projeto. Explique a responsabilidade de cada um.

| **Bounded Context** | **Responsabilidade**                                          | **Subdomínios Relacionados**                       |
| ------------------- | ------------------------------------------------------------- | -------------------------------------------------- |
| Relacionamentos     | Gerencia os relacionamentos entre os usuários e os parceiros. | Cadastro de Usuários, Relacionamento com parceiros |
| Tesouraria          | Responsavel pelas movimentações financeiras e smart contracts | Pagamentos, Gestão de benefícios                   |
| Campanha            | Gerenciamento de campanhas digitais                           | Gestão de Campanhas                                |

---

<!-- ## 5. Comunicação entre os Bounded Contexts
Explique como os bounded contexts vão se comunicar. Use os padrões de comunicação, como:
- **Mensageria/Eventos (desacoplado):** Ex.: O Contexto de Consultas emite um evento "Consulta Finalizada", consumido pelo Contexto de Pagamentos.
- **APIs (síncrono):** Ex.: O Contexto de Pagamentos consulta informações de preços no Contexto de Consultas.

| **De (Origem)**       | **Para (Destino)**     | **Forma de Comunicação** | **Exemplo de Evento/Chamada**            |
| --------------------- | ---------------------- | ------------------------ | ---------------------------------------- |
| Contexto de Consultas | Contexto de Pagamentos | Mensageria (Evento)      | "Consulta Finalizada"                    |
| Contexto de Cadastro  | Contexto de Consultas  | API                      | Obter informações de um Paciente pelo ID |

--- -->

## 6. Definição da Linguagem Ubíqua
Liste os termos principais da Linguagem Ubíqua do projeto. Explique brevemente cada termo.

| **Termo**    | **Descrição**                                              |
| ------------ | ---------------------------------------------------------- |
| Usuário      | Consumidor final da plataforma.                            |
| Investidor   | Pessoa que vai fazer investimentos dentro da plataforma.   |
| Empreendedor | Representantes das empresas em busca de investimento.      |
| Campanha     | Projeto cadastrado pelo empreendedor para captar recursos. |
| TIL          | Token de Impacto Local.                                    |
| TAP          | Token de Ativo Produtivo.                                  |
| TCN          | Token de Cota de Negócio.                                  |
| TRED         | Token de Crédito.                                          |
| TOVE         | Token de Governança.                                       |

---

## 7. Estratégia de Desenvolvimento
Para cada tipo de subdomínio, explique a abordagem para implementação:
- **Core Domain:** Desenvolver internamente com foco total.
- **Supporting Subdomain:** Desenvolver internamente ou parcialmente terceirizar.
- **Generic Subdomain:** Usar ferramentas ou serviços de mercado.

| **Subdomínio** | **Estratégia** | **Ferramentas ou Serviços (se aplicável)** |
| -------------- | -------------- | ------------------------------------------ |
| Gestão de Campanhas          | Desenvolvimento interno.                                 | Dotnet, React    |
| Cadastro de Usuários         | Interno com uso de Auth0 para login.                     | Auth0, NodeJS    |
| Pagamentos                   | Desenvolvimento interno e terceiros com smartcontract.   | Solidity         |
| Gestão de benefícios         | Desenvolvimento interno e terceiros com smartcontract    | Solidity         |
| Relacionamento com parceiros | Software terceiro                                        | SAP              |

---
<!-- 
## 8. Diagrama Visual (Opcional, mas Recomendado)
Desenhe um diagrama que mostre:
- Os bounded contexts.
- Como eles se comunicam.
- A relação com os subdomínios.

Use ferramentas como **Miro**, **Lucidchart** ou mesmo papel e caneta para criar seu diagrama e adicionar ao projeto.

--- -->
<!-- 
## Dicas para Apresentação
- Explique cada parte do design, focando no **Core Domain** (o coração do negócio).
- Justifique por que certos subdomínios foram classificados como Supporting ou Generic.
- Destaque como a comunicação entre bounded contexts foi pensada para ser escalável.

---

Boa sorte com a dinâmica! 🚀 -->
