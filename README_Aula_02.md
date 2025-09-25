# 📚 Design Estratégico do Projeto

## 📌 Aula 2: Mapeamento de Contextos (Context Mapping)

### **1️⃣ Objetivo da Aula**
Nesta aula, vamos:<br>
✅ Explorar como **Bounded Contexts** se relacionam entre si.  
✅ Aplicar **Context Mapping** para visualizar dependências entre contextos.  
✅ Criar um **diagrama de Context Mapping** para um projeto.  

---

### **2️⃣ Atividade Prática: Context Mapping no Projeto**

📌 **Objetivo:**  
Identifique os **Bounded Contexts** do projeto e criar um **Context Map**, definindo as relações entre eles.

📌 **Instruções:**  
1️⃣ **Escolha um projeto** (real ou fictício). Ou utilize o seu projeto da aula 1. Pode ser um e-commerce, um sistema de saúde, um banco digital.<br>
2️⃣ **Liste os Bounded Contexts** que fazem parte do sistema.  
3️⃣ **Defina os relacionamentos** entre os contextos usando os padrões do Context Mapping (**Customer-Supplier, Shared Kernel, Anticorruption Layer, etc.**).  
4️⃣ **Crie um diagrama** representando o Context Map.  
5️⃣ **Justifique suas escolhas** (por que cada relacionamento foi modelado dessa forma?).  

📌 **Colheita digital**  

| **Origem**               | **Destino**              | **Tipo de Relacionamento**       | **Explicação** |
|--------------------------|-------------------------|--------------------------------|---------------|
| Relacionamentos          | Campanhas               | **Conformist**                 | Uma campanha apenas consome as informações de usuários e parceiros |
| Campanha                 | Relacionamentos         | **Customer-Supplier**          | O contexto de Relacionamentos deve apenas consumir os dados de campanha, sem poder alterar os dados |
| Tesouraria               | Campanhas               | **Anticorruption Layer (ACL)** | Manter os dois contextos isolados para não impactar a area de tesouraria |
| Campanhas                | Tesouraria              | **Customer-Supplier**          | O contexto de campanha deve apenas fornecer os dados para Tesouraria |
| Tesouraria               | Relacionamentos         | **Anticorruption Layer (ACL)** | Manter os dois contextos isolados para não impactar a area de tesouraria |

**Diagrama**

<img src="diagrama.drawio.svg"  height=600>
<!-- 
📌 **Formato de Entrega:**  
- O trabalho pode ser entregue em **Markdown (.md), PDF ou apresentação (PPT)**.  
- O diagrama pode ser anexado como **imagem** ou **link para uma ferramenta online**.  
- Entrega via **repositório Git** ou outra plataforma definida pelo professor.   -->
<!-- 
📌 **Ferramentas para Criar o Diagrama:**  
- [Miro](https://miro.com/)  
- [Lucidchart](https://www.lucidchart.com/)  
- [Figma](https://www.figma.com/)   -->


## 📌 Aula 3: Próximos Passos  
Na próxima aula, vamos explorar **Design Tático**, abordando:  
🔹 **Entidades vs. Value Objects** – Como diferenciar e modelar corretamente.  
🔹 **Agregados** – Como definir o agregado raiz e garantir consistência.  
🔹 **Repositórios** – Como separar persistência da lógica de domínio.  

📌 **Prepare-se!** Tente aplicar **Context Mapping** no seu projeto antes da próxima aula.  

---

**📢 Bom trabalho! Nos vemos na próxima aula! 🚀**  
