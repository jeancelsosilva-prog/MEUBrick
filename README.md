# MEUBrick

App de bolso para flip de console: manual, régua de compra, simulador de giro
e registro dos negócios feitos (markup, dias em estoque, R$/hora, faturamento por mês).

Um arquivo HTML, sem build, sem dependência de CDN. Roda offline.

---

## 1. Subir no GitHub Pages

1. Crie um repositório novo (pode ser público ou privado com Pages habilitado).
2. Envie **todos** os arquivos desta pasta para a raiz do repositório:

   ```
   index.html
   manifest.webmanifest
   sw.js
   .nojekyll
   icon-32.png  icon-120.png  icon-152.png  icon-167.png
   icon-180.png icon-192.png  icon-512.png  icon-maskable-512.png
   ```

   O arquivo `.nojekyll` é obrigatório — sem ele o GitHub Pages ignora alguns arquivos.

3. **Settings › Pages › Source: Deploy from a branch**, branch `main`, pasta `/ (root)`. Salve.
4. Em um ou dois minutos o endereço fica disponível em
   `https://<seu-usuario>.github.io/<nome-do-repo>/`

Todos os caminhos são relativos (`./`), então funciona em qualquer nome de repositório,
sem ajuste.

## 2. Instalar no iPhone

1. Abra o endereço **no Safari** (não funciona pelo Chrome no iOS).
2. Toque no botão de compartilhar (o quadrado com a seta para cima).
3. **Adicionar à Tela de Início** → Adicionar.
4. O ícone aparece na tela inicial. Abrindo por ali, o app roda em tela cheia,
   sem a barra do Safari, e funciona sem internet.

## 3. Atualizar depois

Substitua os arquivos no repositório. O app busca a versão nova ao abrir com internet.
Se quiser forçar, mude a linha `const CACHE = 'meubrick-v1';` no `sw.js` para `'meubrick-v2'`.

## 4. Onde ficam os seus dados

Os negócios, as marcações e os valores das calculadoras ficam guardados **no próprio
aparelho** (localStorage) — não sobem para lugar nenhum e ninguém mais vê.

Isso tem uma consequência: se você limpar os dados do Safari, trocar de celular ou
remover o app da tela inicial, os registros vão junto.

**Exporte um backup uma vez por mês.** Toque no ícone de banco de dados no topo direito:

- **Backup (.json)** — restaura tudo exatamente como estava.
- **Planilha (.csv)** — abre no Excel ou no Numbers, com markup, margem, dias e R$/hora
  já calculados por linha.

No iPhone o arquivo cai em *Arquivos › Downloads*. Mande para você mesmo no WhatsApp
ou salve no iCloud.

---

## Taxas embutidas (verificadas em 17/09/2026)

| Canal | Taxa |
|---|---|
| PIX / dinheiro | 0% |
| Débito (InfiniteTap) | 1,37% |
| Crédito 1x | 3,15% |
| Crédito 10x | 11,06% |
| Crédito 12x | 12,40% |
| Mercado Livre Clássico | 13% + R$ 55 de frete |
| Shopee | 14% + R$ 26 fixos |

Taxas mudam. Reconfira a cada trimestre e ajuste em `index.html`,
na constante `CANAIS` (perto do início do `<script>`).

Deslocamento fica **fora** de todas as contas, por escolha: o custo é abatido
rodando Uber no trajeto.
