## Configuração de Domínio na Cloudflare

### 1. Adicionar domínio

1. Acesse a conta da **Cloudflare (Growth)**
2. Clique em **Integrar um domínio**

---

### 2. Configuração inicial

Siga o modelo abaixo:

![[Pasted image 20260116164719.png]]

- Clique em **Continuar**
- Selecione o plano **Free**

---

### 3. Ajustar DNS

Na próxima etapa:

- **Desative o Proxy (nuvem laranja → cinza)**
- Exclua todos os registros:
    - `NS`
    - `AAAA`

![[Pasted image 20260116164810.png]]

---

### 4. Verificações antes de alterar o IP

Antes de alterar o apontamento principal:

- Verifique se existem registros como:
    - `MX` (e-mail)
    - Webmail
    - Outros serviços vinculados ao domínio

> ⚠️ **Importante:**  
> Se houver, ajuste esses serviços para continuarem funcionando **antes de alterar o IP principal**.

---

### 5. Alterar apontamento do domínio

Agora sim, configure os registros:

#### Registro principal (A)

- Tipo: `A`
- Nome: `@`
- IP: **IP enviado pelo TI**

#### Registro CNAME

- Tipo: `CNAME`
- Nome: `www`
- Valor: `@`

> 💡 Isso garante que o `www` aponte para o domínio principal.

---

> ⚠️ **Atenção**
> 
> - Altere **apenas o registro principal**
> - Não modifique outros registros como:
>     - `ftp`
>     - `mail`
>     - ou similares

---

### 6. Finalizar configuração na Cloudflare

- Clique em **Continuar**
- Siga até a etapa de **Ativação**

---

### 7. Alterar DNS no Registro.br

1. Acesse o **registro.br**
2. Localize o domínio
3. Substitua os DNS atuais pelos fornecidos pela Cloudflare

---

### 8. Ativação de SSL

Após alterar os DNS:

1. Envie um e-mail para o **TI**
2. Solicite a **ativação do SSL**

---

### 9. Verificar propagação do DNS

Aguarde o retorno do TI e valide a propagação:

- Acesse: [https://dnschecker.org](https://dnschecker.org)
- Verifique se o domínio já está apontando para o novo IP
