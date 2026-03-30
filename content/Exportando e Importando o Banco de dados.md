## 🗄️ Importação e exportação do banco de dados

Após verificar a **propagação do DNS**, siga os passos abaixo:

---

### 1. Acessar phpMyAdmin do cliente

1. Acesse:

dominiodocliente.com.br/phpmyadmin

2. Insira os dados das variáveis **`'USER'`** e **`'PASS'`** que estão no código.

---

### 2. Acessar Deploy

1. Entre em:

deploy.buscaclientes.com.br

2. Insira as informações correspondentes que estão **logo acima da seção `// DEPLOY`** no código.

> ⚠️ Se aparecerem avisos, clique em **Ignorar tudo** em todas as vezes que surgir.

---

### 3. Exportar o banco de dados

1. Dentro do deploy, clique no banco existente (localizado abaixo de **Novo BD**)
2. Clique em **Exportar**  
    ![[Pasted image 20260116173039.png]]
3. Clique novamente em **Ignorar tudo** e depois em **Executar**
4. Salve o arquivo exportado no seu computador

---

### 4. Importar o banco no phpMyAdmin do cliente

1. Acesse novamente:

dominiodocliente.com.br/phpmyadmin

2. Insira as mesmas credenciais (`'USER'` e `'PASS'`)
3. Clique no **banco do cliente** (localizado abaixo do botão **Novo**)

> [!IMPORTANTE]  
> Não selecione outro banco, escolha apenas o do cliente.

4. Clique em **Importar**  
    ![[Pasted image 20260116173305.png]]
5. Selecione o arquivo exportado anteriormente
6. Desça a tela e clique em **Importar**

✅ O banco de dados estará importado e pronto para uso.