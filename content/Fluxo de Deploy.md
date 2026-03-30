## Checklist de Acessos e Fluxo de Deploy

Antes de iniciar o **processo de Deploy**, garanta que você possua **todos os acessos** às plataformas necessárias:

- [[Guacamole]]
- [[BitBucket]]
- [[Painel do Busca Cliente]]
- [[Salesforce]]
- [[Contas Google do Busca Cliente]]

> ⚠️ **Importante:** Sem esses acessos, não será possível executar nenhuma etapa do deploy.

---

## 📝 Fluxo do Deploy

Após confirmar os acessos, siga os passos abaixo na ordem indicada:

1. **[[Criando o PR no BitBucket]]** – Preparar e revisar o Pull Request
2. **[[Editando o código]]** – Alterar `geral.php`, configurar reCAPTCHA, Analytics e Tag Manager
3. **[[Acessando o Guacamole]]** – Clonar repositório e preparar ambiente
4. **[[Apontamento de DNS na Cloudflare]]** – Configurar registros e propagação do domínio
5. **[[Exportando e Importando o Banco de dados]]** – Exportar do Deploy e importar no phpMyAdmin
6. **[[Colocando o sitemap.xml]]** – Enviar sitemap para o Google Search Console
7. **[[Finalizando o deploy]]** – Atualizar Salesforce e planilha de fluxo, concluir o processo