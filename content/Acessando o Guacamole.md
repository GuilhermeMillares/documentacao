## Publicação do Projeto via SSH (Servidor + Bitbucket)

### 1. Acessar o servidor do cliente

1. Acesse o [[Guacamole]]
2. Pesquise pelo domínio do cliente
3. Conecte-se ao servidor correspondente

---

### 2. Navegar até a pasta do projeto

Execute os comandos abaixo:

```
cd web  
cd dominiodocliente.com.br  
cd public_html
```

> 💡 Dica: você pode digitar `cd dom` + `TAB TAB` para autocompletar o nome da pasta.

---

### 3. Verificar e limpar a pasta (se necessário)

Liste os arquivos:

```
ls
```

👉 Se aparecer apenas:

- `index.html`
- `robots.txt`

Execute:

```
rm -r *
```

> ⚠️ **Atenção:** esse comando remove todos os arquivos da pasta atual. Use apenas se tiver certeza.

---

### 4. Gerar chave SSH

Para clonar o repositório, é necessário gerar uma chave SSH:

```
ssh-keygen -t rsa -b 4096 -C "contato@buscacliente.com.br"
```

Depois:

- Pressione **Enter 3 vezes** para aceitar os padrões

Agora exiba a chave pública:

```
cat ~/.ssh/id_rsa.pub
```

---

### 5. Adicionar chave no Bitbucket

1. Copie **toda a saída** do comando anterior
2. Acesse o repositório no Bitbucket
3. Vá até as configurações de **SSH Keys**

Siga o exemplo:

![[Pasted image 20260116163724.png]]  
![[Pasted image 20260116163807.png]]

4. Clique em **Add Key**
5. Preencha:
    - **Nome:** domínio do cliente
    - **Key:** cole a chave copiada
6. Clique em **Add Key**

---

### 6. Clonar o repositório no servidor

1. No Bitbucket, clique em **Clone**
2. Altere de **HTTPS** para **SSH**
3. Copie o comando

Agora **adicione `public_html` no final**:

```
git clone git@bitbucket.org:busca-clientes/dominiodocliente.com.br.git public_html
```

4. Execute no servidor

Durante o processo, será solicitado:

yes

Digite `yes` e pressione Enter.

---

### 7. Finalizar

Após o término do clone:

```
exit
```

Pronto! O projeto estará publicado no servidor 🎉

