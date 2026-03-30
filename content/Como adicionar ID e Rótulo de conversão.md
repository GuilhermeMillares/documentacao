## Configuração de Conversões no Google Tag Manager

Agora que você já possui o **ID de conversão** e o **Rótulo de conversão** do cliente, vamos adicioná-los ao Google Tag Manager.

---

### 1. Criar o Vinculador de Conversões

1. Acesse o **Tag Manager** do cliente
2. No menu lateral, clique em **Tags**
3. Clique em **Nova**

![[Pasted image 20260330105656.png]]

4. Na tela que abrir, clique no quadrado branco para abrir o painel lateral
5. Procure por **Google Ads**
6. Selecione **Vinculador de Conversões**

![[Captura de tela 2026-03-30 110015(2).gif]]

7. Em seguida, clique em **Acionamento**
8. Selecione **All Pages**

O resultado deve ficar semelhante a este:

![[Pasted image 20260330110924.png]]

---

### 2. Criar a Tag de Conversão

Agora vamos configurar as conversões que o cliente deseja metrificar.

1. Clique em **Nova Tag**
2. No mesmo painel anterior, selecione:
    - **Acompanhamento de conversões do Google Ads**  
        _(fica logo abaixo do Vinculador de Conversões)_
3. Preencha os campos conforme o exemplo:

![[Pasted image 20260330111251.png]]

> [!important]  
> Utilize o **Código de conversão** e o **Rótulo de conversão** enviados pelo cliente.  
> Essas informações normalmente estão no comentário da tarefa.

---

### 3. Criar a Tag do Google (se solicitado)

Após inserir o código de conversão, pode aparecer uma solicitação para criar uma tag do Google.

![[Pasted image 20260330111822.png]]

- Clique em **Criar tag**
- Na próxima tela, clique em **Salvar** (sem alterações)

![[Pasted image 20260330111918.png]]

---

### 4. Configurar o Acionador (Trigger)

1. Após retornar à tela da tag:
    - Insira o **Rótulo de conversão**
    - Vá até **Acionamento**
2. Clique no botão **"+"** para criar um novo acionador

![[Pasted image 20260330112216.png]]

3. Clique no campo em branco e selecione:
    - **Envio de formulário** (ícone verde)
4. Configure conforme o exemplo:

![[Captura de tela 2026-03-30 113019(2).gif]]

> [!tip]  
> Inicialmente, utilize a condição **"contém form"**.  
> Isso será ajustado posteriormente com base no teste.

> [!warning]  
> **Não esqueça de nomear o acionador corretamente:**
> 
> - Exemplo genérico: `Envio de formulário`
> - Exemplo específico: `Envio de formulário - WhatsApp`

---

### 5. Testar no Modo Preview

1. Volte à tela inicial do Tag Manager
2. Clique em **Visualizar** (ao lado de "Enviar")
3. Insira a URL do site e clique em **Conectar**

Agora o site será aberto para testes.

---

### 6. Validar o Disparo da Tag

1. Realize um teste real:
    - Envio de formulário
    - Clique em botão de WhatsApp
    - Pop-up, etc.
2. Após enviar, volte à tela de preview do Tag Manager

Você verá algo como:

![[Pasted image 20260330114100.png]]

3. Clique no evento disparado (ex: _ADS - Envio para Whatsapp_)

---

### 7. Ajustar a Classe Correta

No evento, identifique a classe correta do elemento.

- Substitua o valor genérico **form** pela classe real
- Exemplo:

form → whatsapp__form

![[Pasted image 20260330114430.png]]

---

### 8. Finalizar

- Salve as alterações
- Clique em **Enviar** se tudo estiver correto

Caso existam outras conversões, repita o processo para cada uma.

---

## ❓ Por que ajustar a classe do acionador?

Se você deixar apenas **"form"**, o acionador será disparado para **qualquer elemento que contenha "form" na classe**.

Ao usar a classe específica (ex: `whatsapp__form`), você garante que:

- Apenas o evento correto será rastreado
- Evita métricas incorretas
- Melhora a precisão dos dados