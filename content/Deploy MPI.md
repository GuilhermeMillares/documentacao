
# 🚀 Como fazer o deploy MPI Solutions


Para realizar o deploy do MPI, siga os mesmos passos descritos no [[content/Fluxo de Deploy|Fluxo de Deploy]].

No entanto, existem **algumas adaptações específicas** necessárias para a publicação do MPI, detalhadas abaixo.

---

### 📧 Exemplo de e-mail para a M3

E-mail: `suporte@m3solutions.com.br`

Assunto: ==Criação de VHost e Banco de Dados - MPI SolutionsCriação de VHost e Banco de Dados - MPI Solutions==

---

Boa tarde,

Solicito, por gentileza, a criação de **VHost** e **Banco de Dados** para o projeto **MPI Solutions**, conforme as informações abaixo:

Informações do Servidor

- **IP:** 149.18.103.138
- **Domínio:** dominio.com.br

Usuários com acesso (Suporte / Deploy)

Favor garantir acesso para os seguintes usuários:

- carlos.almeida
- hiago.maitan
- paulo.roberto
- armando.machado
- alan.agenor
- elisa.mostafa
- weverton.costa
- everton.lima
- guilherme.millares

---

## 🔐 Configuração de SSH

Para este projeto, é necessário criar uma **chave SSH exclusiva**.

### 1. Gerar a chave SSH

```
ssh-keygen -t ed25519 -C "seu_email@dominio.com" -f ~/.ssh/nome_da_chave
```

### 2. Iniciar o agente SSH

```
eval "$(ssh-agent -s)"
```

### 3. Adicionar a chave

```
ssh-add ~/.ssh/mpi_solutions
```

### 4. Criar aliases (opcional, mas recomendado)

```
alias mpi='eval "$(ssh-agent -s)" && ssh-add ~/.ssh/mpi'  
alias busca='eval "$(ssh-agent -s)" && ssh-add ~/.ssh/busca'
```

> [!tip] Dica  
> Os aliases facilitam o carregamento das chaves SSH no dia a dia, evitando repetir comandos manualmente.

---

## 🔐 Acesso para as Ferramentas

### 🛠️ Ferramentas vinculadas ao projeto

As seguintes ferramentas são utilizadas no projeto:

- **Google Analytics**
- **Google Tag Manager**
- **Google Search Console**
- **Google reCAPTCHA**

---

### 📧 Credenciais de acesso
Utilizar as credenciais do e-mail `ferramentasmpisolutions@gmail.com` que estão no canal Deploy - BC do Teams.

---

## 📂 Atualizações no Projeto

### 📁 1. Atualizar pasta `/inc`

- Substitua todos os arquivos da pasta `/inc` pelos arquivos do `.zip` fornecido.

>[!warning] Lembrete
>Baixar a pasta inc zipada no canal do teams Deploy BC

### ✏️ 2. Alterações em arquivos PHP

Edite os arquivos:

- `contato.php`
- `form-coluna-lateral-mpi.php`

Adicione o seguinte trecho dentro do formulário:
```

<div style="position:absolute; left:-9999px;" aria-hidden="true">  
  <label for="atendimento">Não preencha este campo</label>  
  <input type="text" name="atendimento" id="atendimento">  
</div>  
  
<input type="hidden" id="site" name="site" value="<?php echo $_SERVER['REQUEST_URI']; ?>">  
<input type="hidden" id="id_cliente" name="id_cliente" value="<?= $idLeads ?>">
```

> [!tip] Onde inserir esse código
> 
> - No `contato.php`: antes das `<div>` que contêm inputs dentro da `<form>`
> - No `form-coluna-lateral-mpi.php`: após o `label` do campo de mensagem
> 

---

### 🔒 3. Ajuste no `mail.send`

Edite o arquivo `mail.send` e adicione a validação de origem da requisição:

```
// Verificação da origem da requisição  
$allowed_host = "www.SITE.com.br";
```


### 🏷️ 4. Configuração no Tag Manager

Para configurar o **Google Tag Manager (GTM)** no projeto MPI, siga os passos abaixo:

1. Acesse o container do projeto no GTM
2. Clique na opção de **importação de container**
3. Utilize o arquivo: `GTM-MPI.json`
4. Confirme a importação e revise as configurações antes de publicar

---

### 🖼️ Exemplo

![[Pasted image 20260330173918.png]]

> [!tip] Dica
> 
> - Sempre verifique se as tags, triggers e variáveis foram importadas corretamente
> - Caso já existam configurações no container, revise possíveis conflitos antes de publicar
Fora os pontos mencionados acima, seguir o processo padrão do **Busca Cliente**.


### 🖼️ Exemplo

![[Captura de tela 2026-03-30 174042(3).gif]]

> [!tip] Dica
> Clique em salvar no final da página após adicionar o json

---
Fora os pontos mencionados acima, seguir o processo padrão do **Busca Cliente**.
