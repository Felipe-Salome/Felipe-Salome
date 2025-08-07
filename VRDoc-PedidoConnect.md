# VRDoc

## Ambiente de Desenvolvimento

O processo de criação e importação de pedidos Connect via VRPdv depende da integração entre **três plataformas** distintas:

* **VRMaster**: Aplicativo utilizado para gestão.
* **Loja Virtual (e-commerce Connect)**:
  [https://onlinesim.com.br/vrsoftware/](https://onlinesim.com.br/vrsoftware/)
* **Portal de Separação de Pedidos (MobileSim)**:
  [https://simservices.mobilesim.com.br/](https://simservices.mobilesim.com.br/)

Antes de iniciar, certifique-se de que o ambiente está configurado com:

* **Token de acesso e URL da API Connect** (obtidos via VRConnect).
* Menu de configuração no sistema:

  > `Administrativo > Gestão Oferta > Oferta > Parâmetro Oferta > VRConnect`

> ⚠️ **Atenção:**
> Sempre verifique o **CNPJ** e o **Token** configurados no ambiente.
> Se forem utilizados os dados reais de um cliente, o pedido será enviado diretamente para o **ambiente de produção do cliente**, gerando impactos reais.
> Para homologação e testes, utilize sempre **CNPJs e tokens de teste fornecidos para esse fim**.

---

## Documentação do Sistema

<h1 align="center">Regra Técnica de Pedido Connect via VRPdv</h1>

---

### Visão Geral

Para que um **pedido Connect** possa ser criado e posteriormente **importado no VRPdv**, é necessário garantir a consistência e disponibilidade dos **produtos envolvidos**, além da **correta configuração do ambiente VRConnect**.

---

### Requisitos Técnicos

#### 1. Cadastro de Produto

O produto deve estar:

* Cadastrado na **loja virtual Connect** (verificável pelo e-commerce).
* Presente na **base local do VRPdv**.

> Documentação de apoio:
> [Cadastro de Produtos](https://github.com/vrsoftbr/VRDoc)

**Verificação**:
Acesse o site [https://onlinesim.com.br/vrsoftware/](https://onlinesim.com.br/vrsoftware/) e pesquise pelo produto na loja **VRSOFT**.

#### 2. Tabela FORNECEDOR

O banco local precisa conter o **CNPJ da VRSoftware** na tabela `fornecedor`, garantindo o vínculo entre o produto e o marketplace.

---

### Processo de Criação do Pedido

1. Acesse o e-commerce Connect:
   [https://onlinesim.com.br/vrsoftware/](https://onlinesim.com.br/vrsoftware/)

2. Adicione os produtos válidos ao carrinho.

3. Finalize o pedido e anote o número gerado.

---

### Separação do Pedido

1. Acesse o portal MobileSim:
   [https://simservices.mobilesim.com.br/](https://simservices.mobilesim.com.br/)

2. Faça login com as credenciais da planilha de configuração.

3. Navegue até o menu `Separação`.

4. Realize a separação dos itens e conclua.

5. O pedido será movido para a aba `Separado`.

---

### Importação no VRPdv

1. No **VRPdv**, acesse a **Função 218 - Pedido e-Commerce Connect**.

2. Informe:

   * O número do pedido gerado no carrinho.
   * O número do pedido na aba "Separado".

> Os dois devem corresponder ao mesmo pedido.

---

### Conclusão da Venda

Após importação:

* O pedido será convertido em uma venda comum no VRPdv.
* Siga com o processo de finalização: formas de pagamento, descontos, comprovantes etc.
