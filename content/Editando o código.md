## 🔧 Alterações no código e configuração de integrações

Após realizar o **Pull Request (PR)**, será necessário alterar o arquivo `geral.php`.

Você pode fazer isso de duas formas:

1. **Diretamente no BitBucket**
2. **Clonando o repositório localmente**:

git clone https://{dominiodocliente.com.br}

> 💡 O comando de clone pode ser copiado no próprio repositório, selecionando **Clone → SSH** ou **HTTPS**.

---

### ✏️ Editando `geral.php` via BitBucket

1. Clique em **Source**
2. Na barra de pesquisa menor, digite `geral.php`
3. Clique no arquivo e depois em **Edit**
4. A tela irá recarregar. Desça até encontrar a seção:

// Config Final Deploy

Altere **apenas as variáveis** abaixo:

> [!NOTE]
> 
> - `$idProjetoBusca`: Número do painel do cliente. Se não estiver no comentário do Salesforce, consulte o [[Painel do Busca Cliente]]
> - `$tagmanager`: Será gerado posteriormente
> - `$googleSearchConsole`: Será gerado posteriormente
> - `$siteKey`: Será gerado posteriormente
> - `$secretKey`: Será gerado posteriormente

---

### 🔑 Criando as chaves do reCAPTCHA

1. Abra a conta `bcrelatorios`
2. Acesse: [Google reCAPTCHA Admin](https://www.google.com/recaptcha/admin/create)
3. Preencha os campos conforme: ![[Pasted image 20260116152317.png]]
4. Clique em **Enviar**

> ✅ A primeira chave (`site key`) será usada para `$siteKey`  
> ✅ A segunda chave (`secret key`) será usada para `$secretKey`

---

### 📊 Criando a chave do Google Analytics

1. Acesse o Google Analytics com a conta `bcrelatorios`
2. Clique em **Administrador → Criar → Propriedade**
3. Preencha os campos conforme:  
    ![[Pasted image 20260116155235.png]]  
    ![[Pasted image 20260116155433.png]]  
    ![[Pasted image 20260116155506.png]]
4. Selecione **Plataforma: Web**, insira o domínio nos dois campos e clique em **Avançar**  
    ![[Pasted image 20260116155708.png]]  
    ![[Pasted image 20260116155738.png]]
5. Clique em **Criar e Continuar**
6. Na tela **Detalhes do stream Web**, copie o **ID da Métrica** — será usado no Tag Manager

---

### 📌 Criando as chaves do Tag Manager

1. Acesse o [Tag Manager](https://tagmanager.google.com/?authuser=2#/container/accounts/6254899739/containers/240786148/workspaces/3) com a conta `bcrelatoriotag@gmail.com`
2. Clique em **Administrador → + → Criar contêiner**  
    ![[Pasted image 20260116160554.png]]  
    ![[Pasted image 20260116160634.png]]
3. Após criar, clique em **Importar contêiner**
    - Utilize o arquivo `0_1_2.json` (ou solicite ao Everton/Deploy)
    - Clique em **Adicionar ao Espaço de Trabalho**
4. Vá em **Variáveis** no menu esquerdo
5. Altere o **Título** e o valor de **Configuração de Variável** com o **ID da Métrica do Google Analytics**
6. Clique em **Salvar**
7. Clique em **Enviar → Publicar → Pular** para finalizar
8. Copie o número do contêiner e insira na variável `$tagmanager`  
    ![[Pasted image 20260116161500.png]]

---

### 🌐 Criando a propriedade no Google Search Console

1. Acesse o Search Console com a conta `bcrelatorios5`
2. Clique em **Adicionar propriedade → Prefixo URL**  
    ![[Pasted image 20260116162003.png]]
3. Insira os dados conforme: ![[Pasted image 20260116162100.png]]
4. Selecione **Tag HTML**, copie a tag `<meta>` e extraia apenas o hash de `content="*hash*"`  
    ![[Pasted image 20260116162341.png]]
5. Insira o hash na variável `$googleSearchConsole`

> 💻 Se estiver usando VSCode, faça commit e push:

git add .  
git commit -m "Config Deploy"  
git push origin main

O código será atualizado no repositório.

---

### 🛠 Alterando `Client.inc.php`

Após receber do TI o **nome, usuário e senha**, insira:

> [!NOTE]
> 
> - `'USER'` = nome com **menos caracteres**
> - `'PASS'` = senha enviada pelo TI
> - `'DBSA'` = nome com **mais caracteres**

> 💻 Após alterar, realize commit e push da mesma forma que fez com `geral.php`.