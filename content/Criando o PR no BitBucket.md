## 📧 Solicitação de Vhost

Antes de qualquer alteração no código, é necessário solicitar a criação do **Vhost** e a autorização para os usuários de **Suporte/Deploy**:

1. Envie um e-mail para:  
    `suporte@m3solutions.com.br`
2. Para o modelo de e-mail, consulte:
    - **Everton**
    - **Hiago**

---

## 💻 Trabalhando com Pull Request no Bitbucket

### 1. Acessar o repositório

1. Abra o [[BitBucket]]
2. Na barra de pesquisa, cole o domínio do cliente
3. Selecione o repositório correspondente

---

### 2. Criar ou verificar Pull Request

1. No repositório, clique em **Pull Requests**
2. Se já houver um PR existente → apenas **faça o merge**
3. Se não houver PR → clique em **Criar Pull Request**

> Exemplo da tela de criação do PR:  
> ![[Pasted image 20260116145222.png]]  
> ![[Pasted image 20260116145256.png]]

---

### 3. Configurações do Pull Request

- O PR deve migrar o código da **branch `produção`** (desenvolvimento) para a **branch `main`** (ambiente principal)
- Marque a opção para **deletar a branch de desenvolvimento** após o merge
- Clique em **Create Pull Request**

---

### 4. Realizar o Merge

1. Após criar o PR, você será direcionado para a tela do Pull Request
2. Caso o botão azul **Merge** não apareça, clique nos **três pontinhos** e selecione **Merge**
3. O PR será concluído com sucesso ✅