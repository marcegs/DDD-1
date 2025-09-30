# 📚 Trabalho - Design Tático no DDD

## 📌 Objetivo
Criar as **Entidades, Value Objects, Agregados e Repositórios** do seu projeto, aplicando o **Design Tático do DDD**.

---

## 📂 **1️⃣ Conceitos Fundamentais**

### **🧩 Entidades vs. Objetos de Valor**
📌 **Entidades** têm **identidade única** e podem mudar ao longo do tempo.
📌 **Objetos de Valor** não possuem identidade própria e são **imutáveis**.

## **📝 2️⃣ Atividade Prática: Modelagem do Domínio**

📌 **Objetivo:**  
Criar as **Entidades, Value Objects, Agregados e Repositórios** do seu projeto.  

📌 **Instruções:**  
1️⃣ **Identifique as Entidades e Value Objects** do seu domínio.  
2️⃣ **Defina os Agregados e seu Aggregate Root**.  
3️⃣ **Implemente um diagrama mostrando as relações entre os elementos**.  
4️⃣ **Crie a interface do repositório para persistência do agregado**.  

💡 **Colheita Digital:**  

| **Elemento**      | **Entidade ou Value Object?** | **Justificativa**                                                             |
|-------------------|-------------------------------|-------------------------------------------------------------------------------|
| **Investidor**    | Entidade                      | Tem um ID único, dados atualizáveis ​​e pode interagir com muitas campanhas.    |
| **Empreendedor**  | Entidade                      | Tem um ID único, dados atualizáveis ​​e pode criar com muitas campanhas.        |
| **Consumidor**    | Entidade                      | Tem um ID único, dados atualizáveis ​​e pode consumir de vários empreendedores. |
| **Endereço**      | Value Object                  | Organiza as informações de endereço dos usuários.                             |
| **Wallet**        | Value Object                  | Guarda e valida o endereço da wallet dos usuários.                            |
| **CPF**           | Value Object                  | Guarda e valida o CPF dos usuários.                                           |

---

### **🏗️ Agregados e Aggregate Root**
- Um **Agregado** agrupa entidades e objetos de valor que fazem parte de uma mesma regra de consistência.  
- O **Aggregate Root** é a entidade principal que controla a consistência do agregado.  

📌 **Agregados Colheita Digital:**  
- **Campanha** (Aggregate Root)
  - Investidor (Entidade)
  - Empreendedor (Entidade)
- **Venda** (Aggregate Root)
  - Consumidor (Entidade)

📌 **Regras de Negócio no Agregado:**  
- Cada **Campanha** pertence a um único **Empreendedor**.
- Um **Empreendedor** pode possuir várias **Campanhas**.
- Um **Investidor** pode investir em várias **Campanhas**.
- Os usuários podem assumir papel de **Empreendedor**, **Investidor** e **Consumidor**.

---

### **🗃️ Repositórios**
Os **Repositórios** são responsáveis por **persistir e recuperar** agregados.  
✅ Devem **trabalhar apenas com Aggregate Roots**.  
✅ **Não devem expor entidades internas do agregado diretamente**.  

💡 **Repositórios Colheita Digital:**  

```kotlin
data class Campaign(
	val alias: String,
	val createdAt: String,
	val description: String,
	val hash: String,
	val id: String,
	val title: String,
	val updatedAt: String,
	val valor: Float,
)

data class Wallet(
	val hash: String
)

interface ICampaignRepository {
    fun create(campaign: Campaign)
    fun delete(campaignIdOrAlias: String)
    fun find(campaignIdOrAlias: String)
    fun update(campaign: Campaign)
    fun invest(amount: Float, campaignIdOrAlias: String, userWallet: Wallet)
}

interface ISaleRepository {
    fun order(productIds: List<String>, userId: String)
}
```
